<template>
	<main class="quizgame">
		<section class="quiz" v-if="!quizCompleted">
			<div class="quiz-info">
				<span class="question">{{ getCurrentQuestion.question }}</span>
				<!--<span class="score">Правильные {{ score }}/{{ questions.length }}</span> -->
			</div>
			
			<div class="options">
				<label 
					v-for="(option, index) in getCurrentQuestion.options" 
          :key="index"
					:for="'option' + index" 
					:class="`option ${
						getCurrentQuestion.selected == index 
							? index == getCurrentQuestion.answer 
								? 'correct' 
								: 'wrong'
							: ''
					} ${
						getCurrentQuestion.selected != null &&
						index != getCurrentQuestion.selected
							? 'disabled'
							: ''
					}`">
          <div class="form-radio-hidden">
            <input
						type="radio" 
						:id="'option' + index" 
						:name="getCurrentQuestion.index" 
						:value="index" 
						v-model="getCurrentQuestion.selected" 
						@change="SetAnswer" 
					/><!--:disabled="getCurrentQuestion.selected"-->
					<span class="radio"></span><span class="text">{{ option }}</span>
          </div>
					
				</label>
			</div>
			
				<my-button  style="margin-bottom: 100px;"
				@click="NextQuestion" 
				:disabled="!getCurrentQuestion.selected">
				{{ 
					getCurrentQuestion.index == questions.length - 1 
						? 'Завершить квиз' 
						: getCurrentQuestion.selected == null
							? 'Выберите ответ'
							: 'Следующий вопрос'
				}}
			</my-button>
			
			
		</section>

		<section v-else class="end">
			<h2 style="margin: 30px 0 30px 0;">Вы завершили квиз</h2>
			<h3 style="font-size: 30px; margin-bottom: 50px;">Количество правильных ответов: {{ score }}/{{ questions.length }}</h3>
		
      <h2 style="margin-bottom: 20px;">Другие квизы:</h2> 
      <VWrapper style="display: flex; width: 80%; margin: 0 auto;"/>
		</section>


	</main>
</template>

<script>
import VWrapper from "@/components/VWrapper.vue"
export default {
  components: {
    VWrapper,
  }
}
</script>

<script setup>
import { ref, computed } from 'vue'
const questions = ref([
  {
	question: 'Что должен знать фронтенд-разработчик? Назовите три ключевых технологии.',
	answer: 0,
	options: [
		'HTML, CSS и JavaScript.',
		'Kotlin, PHP и JavaScript.',
		'PHP, HTML и CSS.'
	],
	selected: null
  },
  {
	question: 'К какому JS-фреймворку относится метод beforeMount()?',
	answer: 2,
	options: [
		'Ember',
		'React',
		'Vue'
	],
	selected: null
  },
  {
	question: 'className — из какого это JS-фреймворка?',
	answer: 1,
	options: [
		'jQuery',
		'React',
		'Angular'
	],
	selected: null
  }
])
const quizCompleted = ref(false)
const currentQuestion = ref(0)
const score = computed(() => {
	let value = 0
	questions.value.map(q => {
		if (q.selected != null && q.answer == q.selected) {
			console.log('correct');
			value++
		}
	})
	return value
})
const getCurrentQuestion = computed(() => {
	let question = questions.value[currentQuestion.value]
	question.index = currentQuestion.value
	return question
})
const SetAnswer = (e) => {
	questions.value[currentQuestion.value].selected = e.target.value
	e.target.value = null
}
const NextQuestion = () => {
	if (currentQuestion.value < questions.value.length - 1) {
		currentQuestion.value++
		return
	}
	
	quizCompleted.value = true
}
</script>

<style>
.quizgame {
  display: flex;
  width: 74%;
  height: 100%;
  margin: 0 auto;
}

.quiz-info {
  padding: 100px 0 30px 0;
}

.question {
  font-size: 40px;
  font-weight: 300;
  line-height: 145%;
}

.options {
  font-size: 32px;
  line-height: 145%;
  margin-bottom: 30px;
}

.end {
	text-align: center; align-items: center;
}
/* Определяем размещение по горизонтали элементов обернутых в label */
.form-radio-hidden{
  display: flex;
  flex-direction: row;
  position: relative;
  align-items: center;
  text-align: center; 
}

/* Скрываем штатные радио-кнопки */
.form-radio-hidden input{
  position: absolute;
  opacity: 0;
  display: block;
  height: 0;
  width: 0;
}

/* Устанавливаем параметры элементов, заменяющих штатные радио-кнопки */
.form-radio-hidden .radio{
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  display: inline-block;
  position: relative;
  height: 20px;
  width: 20px;
  border-radius: 20px;
  margin-right: 8px;
  border: 1px solid #B18CFF;

  box-shadow: 0 0 4px 0 rgba(0,0,0,0.1);
  cursor: pointer;
  outline: none;
  box-sizing: border-box;
  transition: .5s all;
}

/* Устанавливаем параметры элементов, заменяющих штатные радио-кнопки при наведении */
.form-radio-hidden:hover .radio{
  background-color: #f9f9f9;
  box-shadow: inset 1px 2px 3px 0 rgba(0,0,0,0.1);
}

/* Устанавливаем параметры элементов, заменяющих штатные выбранные радио-кнопки */
.form-radio-hidden input:checked + .radio{
  border-color: #7000FF;
  box-shadow: inset 1px 2px 3px 0 #7000FF(0,0,0,0.1);
  cursor: pointer;
}

/* Добавляем декор */
.form-radio-hidden:hover .radio::before, .form-radio-hidden input:checked + .radio::before{
  content: '';
  position: absolute;
  width: 8px;
  height: 8px;
  border-radius: 8px;
  background-color: #B18CFF;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
}
.form-radio-hidden input:checked + .radio::before{
  background-color: #7000FF;
  box-shadow: 1px 2px 2px 0 rgba(0,0,0,0.2);
}

/* Устанавливаем параметры подписей выбранных радио-кнопок */
.form-radio-hidden input:checked + .radio + .text{
  color: #7000FF;
  cursor: pointer;
}

</style>
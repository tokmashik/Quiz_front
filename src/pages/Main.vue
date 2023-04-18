<template>
  <div class="mainvr">
    <div class="main_text">
      <h2>CREEATE A QUIZ</h2>
      <h2>THIS IS YOUR WAY</h2> 
      <h2>TO ALL WHAT YOU</h2> 
      <h2>NEEEED</h2> 
    
    </div>
    <div class="mainphoto">
          <img src="@/assets/MainPageIMG.png" alt="main photo">
    </div>
  </div>

  <div class="instr_wr">
    <div class="instr_main">
          <h1>How to make a quiz</h1>
    </div>
  <div class="instr">
    <div class="instr_card">
    <h2>1</h2>
    <h3>Choose your quiz type    </h3>
    <h4>Built for both students, lead capture and leisure, you can make your own trivia quiz, personality tests, polls, and surveys. </h4> 
    </div>
    <div class="instr_card">
    <h2>2</h2>
    <h3>Write your questions</h3>
    <h4>Add your question from more than 4 types, tick the correct answer and repeat. </h4> 
    </div>
    <div class="instr_card">
    <h2>3</h2>
    <h3>Share with your network</h3>
    <h4>Send out your quiz via a direct link, embed on your website or share on social and start getting responses right away.</h4> 
  </div>
  </div>
      
</div>
<div class="h2quizzes">
      <h2>
    Quizzes:
  </h2>
</div>

<div class="Quizzesmain">

  <VWrapper/>
</div>


</template>

<script>
import VWrapper from "@/components/VWrapper.vue"
export default {
  components: {
    VWrapper 
  },
  data() {
    return {
      quizzez: [
        {id: 1, title: "1erererere"},
        {id: 2, title: "2erererere"},
        {id: 3, title: "3erererere"},
        {id: 4, title: "4erererere"},
      ]
    }
  }
}
</script>

<style>

</style>

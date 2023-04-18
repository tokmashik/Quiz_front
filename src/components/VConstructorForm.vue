<template>
      <form @submit.prevent>
  <div class="constructor">
    <div class="contein">
      <h2 style="text-align: center; margin-bottom: 20px">Create an awesome quiz in minutes</h2> 
      <my-input class="qst"
      placeholder="Вопрос" 
      v-model="post.title">
      </my-input>
      <div class="varansw">
      <my-input class="answ"
      placeholder="Вариант ответа"
      v-model="post.a1">
      </my-input>
      <my-input style="margin-left: 6.5%;" class="answ"
      placeholder="Вариант ответа"
      v-model="post.a2">
      </my-input>
      </div>
      <div class="varansw">      
        <my-input class="answ"
      placeholder="Вариант ответа"
      v-model="post.a3">
      </my-input>
      <my-input style="margin-left: 6.5%;" class="answ"
      placeholder="Вариант ответа"
      v-model="post.a4">
      </my-input>
      </div>
      <my-button style="align-self: center;  margin-left: 67.5%; margin-top: 15px; margin-bottom: 60px;   "
      @click="createPost"
      >Add</my-button>
  </div>
  </div>
  </form>
  </template>
  
  <script>
  export default {
    data() {
        return {
            post: {
                title: '',
                a1: '',
                a2: '',
                a3: '',
                a4: ''
            }
        }
    },
    methods: {
        createPost() {
        this.post.id = Date.now();
        this.$emit('create', this.post)
        this.post = {
                title: '',
                a1: '',
                a2: '',
                a3: '',
                a4: ''
            }        
        },
    }
  }
  </script>
  
  <style scoped>
.constructor {
  width: 76%;
  margin: 0 auto;  justify-content: center;
}

.contein {
  width: 100%;
  margin-top: 40px;
}

.qst {
  width: 50%;
  margin-left: 25%;
}

.varansw {
  display: flex;
  margin-left: 25%;
}
.answ{
  width: 30%;  display: flex;
}
  </style>

<template>
  <button class="quizzes">
      <slot></slot>
  </button>
</template>

<script>
export default {
name: 'my-quizzes'
}
</script>


<style scoped>

  
</style>


<!--.quizzes { 
  display: inline-block;
  cursor: pointer; 
  font-size: 16px;
  text-decoration:none;
  color:#ffffff;
  background: linear-gradient(255.21deg, rgba(17, 14, 23, 0.53) 4.77%, rgba(17, 14, 23, 0.28) 100%);
  border: 2px solid #7000FF;
  border-radius: 10px;
  transform: matrix(-1, 0, 0, 1, 0, 0);
}
.quizzes:hover {
  background:#B18CFF;
  color:#ffffff;
  border: 2px solid  #7000FF;
  transition: all 0.9s ease;
  }-->
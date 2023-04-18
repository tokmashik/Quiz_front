<template>
    <div class="mainquizzes">
        <h2>
    Quizzes:
  </h2>
  <VWrapper/>
    </div>
</template>

<script>
import VWrapper from "@/components/VWrapper.vue"
export default {
  components: {
    VWrapper,
  }
}
</script>

<style>

.mainquizzes {
  width: 65%;
  margin: 0 auto;
  
}

.mainquizzes h2 {
  text-align: center; 
}
</style>
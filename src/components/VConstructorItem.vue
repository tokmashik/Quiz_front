<template>
  <div class="post">
        <div>
            <div>Name: {{ post.title }}</div>
            <div>Discription: {{ post.a1 }}</div>
            <div>Discription: {{ post.a2 }}</div>
            <div>Discription: {{ post.a3 }}</div>
            <div>Discription: {{ post.a4 }}</div>
        </div>
        
            <my-button
            @click="$emit('remove', post)">
                Delete
            </my-button>
          </div>
</template>
  
  <script>
export default {
    props: {
        post: {
            type: Object,
            required: true
        }
    }
  }
  </script>
  
<style scoped>
  .post {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>

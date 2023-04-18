<template>
  <div v-if="posts.length > 0">
        <post-item 
        v-for="post in posts" 
        :post="post"
        :key="post.id"
        @remove="$emit('remove', post)"
        />
    </div>
    <h2 v-else>
        no
    </h2>
</template>
  
  <script>
  import VConstructorItem from './VConstructorItem.vue';
export default {
  components: {VConstructorItem},
    props: {
        posts: {
            type: Array,
            required: true
        }
    }
  }
  </script>
  
<style scoped>
  .posts {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
  }
</style>

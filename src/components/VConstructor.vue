<template>
 <div>
    <VConstructorForm @create="createPost"/>
    <VConstructorList v-bind:posts="posts"
    @remove="removePost"/> 
  </div>
  </template>
  
  <script>
  import VConstructorForm from "@/components/VConstructorForm.vue"
  import VConstructorList from "@/components/VConstructorList.vue"
  import axios from 'axios'
  export default {
    components: {
      VConstructorForm,
      VConstructorList,
      
    },
  
    data() {
      return {
        posts: [
          {id:1, title: 'post1', a1: 'discriptions',a2: 'discriptions',a3: 'discriptions',a3: 'discriptions'}, 
        ],
      }
    },
  
    methods: {
      createPost(post) {
        this.posts.push(post);
      },
      removePost(post) {
        this.posts = this.posts.filter(p => p.id !== post.id)
      },
    }
  }
  </script>
  
  <style scoped>

  </style>

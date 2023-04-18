<template>
  <div class="v-catalog">
    <VCatalogItem 
    v-for="card in cards"
    v-bind:key="card.article"
    v-bind:card_data="card"
    @sendArticle="ShowChildArt"/>
  </div>
  </template>
  
  <script>
import VCatalogItem from "@/components/VCatalogItem.vue"
export default {
  components: {
    VCatalogItem,
  },
  data() {
    return {
      cards: [
      { 
        article: "t1",
        image: "1.png", 
        name: "Quiz 1", 
        discription: "discription 1",
        available: true
      },
      { 
        article: "t2",
        image: "2.png", 
        name: "Quiz 2", 
        discription: "discription 2",
        available: true
      },
      { 
        article: "t3",
        image: "3.png", 
        name: "Quiz 3", 
        discription: "discription 3",
        available: true
      },
      { 
        article: "t4",
        image: "4.png", 
        name: "Quiz 4", 
        discription: "discription 4",
        available: true
      },
      { 
        article: "t5",
        image: "5.png", 
        name: "Quiz 5", 
        discription: "discription 5",
        available: true
      },
      { 
        article: "t6",
        image: "6.png", 
        name: "Quiz 6", 
        discription: "discription 6",
        available: true
      }
    ]
    }
  },
  methods: {
    ShowChildArt(data) {
      console.log(data)
    }
  }
}
</script>
  
  <style scoped>
.v-catalog {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  text-align: center;
}
  </style>
  
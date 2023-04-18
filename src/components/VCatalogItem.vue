<template>
    <div class="v-catalog-item">
    <img style="border-radius: 8px;" v-bind:src=" require('../assets/'+ card_data.image)">
    <h3> {{card_data.name}}</h3>
    <h4>{{card_data.discription}}</h4>
    <my-button @click="SendDataToParent">
    Начать
    </my-button>
    <!--<my-button
        @click="$router.push(`/posts/${cards.article}`)"
      >
        Открыть
      </my-button>-->
    </div>
</template>

<script>
export default {
    props: {
        card_data: {
            type: Object,
            default() {
                return {}
            }
        }
    },
    methods: {
        SendDataToParent(){
            this.$emit('sendArticle', this.card_data.article)
        }
    }
}
</script>

<style scoped>
.v-catalog-item {
    flex-basis: 27%;
    padding: 28px;
    margin-bottom: 40px;
    margin-top: 30px;
    box-shadow: 0px 0px 6px rgba(112, 0, 255, 0.25);
    border-radius: 8px;
    align-items: center;
}

.v-catalog-item h3 {
    padding: 5px;
}
.v-catalog-item h4 {
    margin-bottom: 10px;
}

</style>

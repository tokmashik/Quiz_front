<template>
  <div class="app">  
  <navbar></navbar>
    <router-view></router-view>
    <the-footer></the-footer>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar";
import TheFooter from "@/components/TheFooter.vue"

export default {
  components: {
    Navbar,
    TheFooter,
  }
}
</script>

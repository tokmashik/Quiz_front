<template>
  <button class="navbutton">
      <slot></slot>
  </button>
</template>

<script>
export default {
name: 'nav-button'
}
</script>

<style>
.navbutton { 
  margin-left: 20px;
  cursor: pointer; 
  font-size: 20px;
  padding-right: 20px;
  border: 0px;
  color:#E9E9E9;
  background: #1b1b1b00;
  font-family: 'StretchPro';
}

.navbutton:hover {
  color:#7000FF;
  transition: color 1s ease; 
}
</style>

<template>
  <button class="button shadow">
      <slot></slot>
  </button>
</template>

<script>
export default {
name: 'my-button'
}
</script>

<style>
.button { 
  --s: 10px; /* the spread-radius */
  display: inline-block;
  cursor: pointer; 
  font-size: 32px;
  text-decoration:none;
  padding: 26px 135px; 
  color: #ffffff;
  box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.5);
  border: 0px;
  border-radius: 24px;
  background: #1B1B1B;
  transform: translate(0);
  transform-style: preserve-3d;
} 

.shadow:before {
  content:"";
  position: absolute;
  inset: -5px;
  transform: translate3d(10px,10px,-1px);
  background: conic-gradient(from 90deg at 40% -25%, #ffd700, #f79d03, #ee6907, #e6390a, #de0d0d, #d61039, #cf1261, #c71585, #cf1261, #d61039, #de0d0d, #ee6907, #f79d03, #ffd700, #ffd700, #ffd700);
  filter: blur(15px);
}

.button:hover {

}
</style>



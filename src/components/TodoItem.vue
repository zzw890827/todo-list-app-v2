<template>
  <li class="item">
    <input type="checkbox" v-model="isChecked">
    <slot name="item-display" :isChecked="isChecked"></slot>
  </li>
</template>

<script>
  export default {
    props: ['e'],
    name: "TodoItem",
    data(){
      return{
        isChecked: false
      }
    }
  }
</script>

<style scoped>
  .item {
    color: blueviolet;
  }
</style>

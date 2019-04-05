<template>
  <div id="app">
    <input type="text" v-model="inputInfo">
    <button @click="handleClick">Add</button>
    <ul>
      <todo-item v-for="item in list" :item-display="item" :key="item.id">
        <template v-slot:item-display="itemProps">
          <span :style="{fontSize: 20, color: itemProps.isChecked ? 'red': 'blue'}">{{item}}</span>
        </template>
      </todo-item>
    </ul>
  </div>
</template>

<script>
  import TodoItem from './components/TodoItem.vue';

  export default {
    name: 'app',
    components: {
      TodoItem
    },
    data() {
      return {
        inputInfo: '',
        list: []
      }
    },
    methods: {
      handleClick() {
        this.list.push(this.inputInfo);
        this.inputInfo = '';
      }
    }
  }
</script>

<style>

</style>

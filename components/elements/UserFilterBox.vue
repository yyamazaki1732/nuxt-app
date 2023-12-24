<template>
    <div>
      <select style="width: 100px" v-model="userId" @change="filterHandler">
        <option value="1">1</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
        <option value="5">5</option>
        <option value="6">6</option>
      </select>
    </div>
  </template>
  
  <script>
  export default {
    name: 'UserFilterBox',
    data() {
      return {
        userId: ''
      }
    },
    methods: {
      filterHandler() {
        this.$emit('filter-id', this.userId);
      }
    }
  }
  </script>
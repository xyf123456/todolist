<template>
  <div>
    <div>
      <input class="item" v-model="inputValue">
      <button @click="handleSubmit">提交</button>
      <ul>
        <todo-item
          v-for="(item,index) of list"
          :content="item"
          :index="index"
          :key="index"
          @delete="handleDelete">
        </todo-item>
      </ul>
    </div>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  components: {
    'todo-item': TodoItem
  },
  // 作为组件data不是一个属性了，而是一个函数
  data () {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit () {
      // alert(123)
      // this.$data.list.push(this.inputValue)
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete (index) {
      // alert(index)
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>
</style>

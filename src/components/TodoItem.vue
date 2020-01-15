<template>
  <li class="item" @click="handleDelete">{{content}}</li>
</template>

<script>
export default {
  // 子组件接受父组件传来的参数
  props: ['content', 'index'],
  methods: {
    handleDelete () {
      // 输出接受到父组件的传递的数据  向父组件触发一些事件
      // alert(this.index)
      this.$emit('delete', this.index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only ,
scoped的作用：只有本身的组件的样式才能起作用，如果去掉的话则为全局样式-->
<style scoped>
  .item {
    color: aqua;
  }
</style>

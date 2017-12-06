<template>
  <div id="app">
    <HelloWorld/>
    这是初始化的值{{test1}}在app.vue中使用,
    这是getter处理后的值{{getterTest1}}
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import { mapGetters } from 'vuex'
export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data () {
    return {

    }
  },
  computed: {
    // 使用getters的调用辅助函数方法，在此使用...运算符可能会出现语法错误。解决方案：添加.babelrc文件及文件内的内容。
    ...mapGetters([ 
      'getterTest1'
    ]),
    test1 () {
      return this.$store.state.test1; // 使用state内初始化的值
    },
    // getterTest1 () {
    //   return this.$store.getters.getterTest1; //使用getters的值（原始调用方法）
    // }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <div id="app">
    <HelloWorld/>
    这是初始化的值{{test1}}在app.vue中使用,
    这是getter处理后的值{{getterTest1}}
    点击生成mutations处理后的值{{$store.state.newTest1}}
    <button @click='mChangeTest1'>使用mutations修改</button>
    <button @click='changeTest1'>直接修改</button>
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
      return this.$store.state.test1; // 获取state内初始化的值
    },
    // getterTest1 () {
    //   return this.$store.getters.getterTest1; //使用getters的值（原始调用方法）
    // }
  },
  methods:{
    mChangeTest1(){
      // 在此使用dispatch的方式调用相应函数对store内的内容进行修改
      // 与直接修改的差别是 这种方式异步操作，常用于发请求，而直接修改则是同步操作
      this.$store.dispatch('add_test1', 1); 
    },
    changeTest1(){
      this.$store.state.test1 = 3;
    }
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

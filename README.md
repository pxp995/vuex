# vuex

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).


### 使用vuex
1. 安装vuex，建vuex的目录结构－－－见文件夹store
2. 将vuex引入项目 －－－－见main.js
3. 在store－index.js内注入vuex的内容
4. 在state内初始化变量
5. getter相当于vue中的计算属性，将变量缓存起来，只有依赖的值发生变化时才会触发（使用辅助函数调用的方法可能会报错，解决方法见app.vue调用处）
6. 数据的实际在mutation中修改，mutation的回调函数会接受state和要修改的值。


<!--<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
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
</style>-->
<template>

  <div>
    {{msg}}
    <div>
    <input v-model="addmsg" type="text">
    <button @click="handleClick" >添加</button>
    </div>
    <ul>
      <todo-item v-for="list in listArr" :key="list">
        <template v-slot:item="itemProps">
          <span :style="{fontSize: '12px',color: itemProps.isCheck ? 'yellow' : 'red'}">
          {{list}}
          </span>
        </template>
      </todo-item>
    </ul>


    <props
    name="hello world"
    :type="type"
    :is-visible="false"
    title="propDemo"
    :on-change="handlePropChange"
    class="test1"
    :class="['test2']"
    :style="{marginTop: '20px'}"
    style = "margin-top: 10px"
    >

    </props>
    <event :name="name" @change="handleEventChange">

    </event>



  </div>
  <!--<div  >
    &lt;!&ndash; 创建一个 todo-item 组件的实例 &ndash;&gt;
    <todo-item
            v-for="item in groceryList"
            v-bind:todo="item"
            v-bind:key="item.id"
            v-bind:msg="item.text"></todo-item>
  </div>-->
</template>


<script>
  import todoItem from './components/TodoItem'
  import props from './components/Props'
  import event from './components/Event'

  export default {
    name: 'app',

    data() {
      return {
        msg: 'hello world',
        name: 'aaa',
        addmsg: '',
        type: 'success',
        listArr: []
      }
    },
    methods:{
      handleClick() {
        this.listArr.push(this.addmsg)
        this.addmsg = ''
      },
      handlePropChange(type){
        this.type = type
      },
      handleEventChange(val){
        this.name = val
      }
    },
    components: {
      todoItem,
      props,
      event
    }
  }
</script>


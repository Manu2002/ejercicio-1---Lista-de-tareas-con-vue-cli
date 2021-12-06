<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Así es CHARLIE"/>
  <div id="app">
        <h1> {{ title }} </h1>
        
        <TodoList v-if="todos.length" :todos="todos" @del-new="delTodo"></TodoList>
        <p v-else>No hay tareas</p>
            <TodoAdd @add-new="addNew" ></TodoAdd>
            <br>
            <br>
            <TodoDelete @delete-all="delAll"></TodoDelete>
    </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodoList from './components/TodoList.vue'

import TodoAdd from './components/TodoAdd.vue'
import TodoDelete from './components/TodoDelete.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    TodoList,

    TodoAdd,
    TodoDelete
  },
  data() {
      return {
        newTarea: ' ',
        title: 'Cosas que hacer!',
        todos: [
            {
                id: 1,
                descrip: "Aprende Vue",
                done: false
            },
            {
                id: 2,
                descrip: "Dominar Vue",
                done: false
            },
            {
                id: 3,
                descrip: "Finalizar Vue",
                done: false
            }
        
        ]
      }
    },
    methods: {
        delAll(){
            this.todos = []
        },
        addNew(newTodo){
            this.todos.push(newTodo)
        },
        delTodo(index){
            this.todos.splice(index,1);
        }
    }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

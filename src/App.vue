<script>
export default {
  data() {
    return {
      newTodoText: '',
      todos: [],
    }
  },
  methods: {
    addTodo() {
      this.todos.push({
        isDone: false,
        text: this.newTodoText,
      })
      this.newTodoText = ''
    },
    deleteTodo() {
      this.todos = this.todos.filter((todo) => !todo.isDone)
    },
  },
}
</script>

<template>
  <h2 id="title">ToDoアプリ</h2>

  <br/><br/>
  <input type="text" v-model="newTodoText" />
  <button @click="addTodo">追加</button>
  <button @click="deleteTodo">削除</button>
  <br/><br/>

  <p>リスト項目</p>
  <p v-if="todos.length == 0">未投稿です。</p>
  <ui v-else>
    <li v-for="todo in todos">
      <input type="checkbox" v-model="todo.isDone"/>
      <span :class="{'todo-done': todo.isDone}">{{ todo.text }}</span>
    </li>
  </ui>
  
</template>

<style>
body {
  background-color: #eee;
}

.todo-done {
  text-decoration: line-through;
}
</style>
<script>
export default {
  data() {
    return {
      list_data: [
        {
          data: 'homework'
        },
        {
          data: 'test'
        }
      ]
    }
  },
  methods: {}
}
</script>

<template>
  <h2 id="title">ToDoアプリ</h2>
  <br/><br/>
  <input type="text"/>
  <button>追加</button>
  <button>削除</button>
  <br/><br/>
  <p>リスト項目</p>
  <div v-for="item in list_data">
    <input type="checkbox"/>
    <span>テスト</span>
    <p>{{ data }}</p>
  </div>

</template>

<style>
#title {
  top: 20px;
}

body {
  background-color: #eee;
}

.todo-done {
  text-decoration: line-through;
}
</style>
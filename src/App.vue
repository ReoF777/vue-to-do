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
      ],
      input: {
        input_data: '',
      }
    }
  },
  methods: {
    addItem() {
      this.list_data.push({
        data: this.input.input_data,
      })
    },
    deleteItem() {

    },
  }
}
</script>

<template>
  <h2 id="title">ToDoアプリ</h2>
  <br/><br/>
  <input type="text" v-model="input.input_data"/>
  <button @click="addItem">追加</button>
  <button @click="deleteItem">削除</button>
  <br/><br/>
  <p>リスト項目</p>
  <div v-for="item in list_data">
    <input type="checkbox"/>
    <span>{{ item.data }}</span>
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
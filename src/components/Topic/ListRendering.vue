<template>
  <div class="try3">

    <p style="margin-top:20px">
      We will start learn about
    </p>
    <h6 :class="titleClass"> List Rendering </h6>
    <b-container>
      <b-row style="margin-top: 20px;">
        <b-col md="2"> Input </b-col>
          <form @submit.prevent="addTodo">
            <input v-model="newTodo">
            <button style="margin-left:20px"> Add Todo</button>
          </form>
      </b-row>
      <b-row>
        <b-col md="4" style="margin-top: 20px;">
          <ul>
            <li v-for="todo in todos" :key="todo.id" style="text-align:left">
              {{ todo.text }}
              <button @click="removeTodo(todo)">X</button>
            </li>
          </ul>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>

// give each todo a unique id
let id = 0

export default {
  data() {
    return {
      text: '',
      titleClass: 'titleList',
      newTodo: '',
      todos: [
        { id: id++, text: 'Learn HTML' },
        { id: id++, text: 'Learn JavaScript' },
        { id: id++, text: 'Learn Vue' }
      ]
    }
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo })
      this.newTodo = ''
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo)
    }
  }
}

</script>

<style>
    .titleList {
        color: rgb(218, 10, 169);
    }
</style>
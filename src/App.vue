<script>
import { trackSlotScopes } from "@vue/compiler-core";
import Header from "./components/Header.vue";
import Todos from "./components/Todos.vue";

export default {
  name: "App",
  components: {
    Header,
    Todos,
  },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    deleteTodo(id) {
      if (confirm("You Sure Mate?")) {
        this.todos = this.todos.filter((todo) => todo.id !== id);
      }
    },
    toggleReminder(id){
      this.todos = this.todos.map((todo)=>todo.id === id?{...todo, reminder: !todo.reminder}: todo)
    }
  },
  created() {
    this.todos = [
      {
        id: 1,
        title: "School",
        day: "June 2nd",
        reminder: true,
      },
      {
        id: 2,
        title: "Doc",
        day: "March 3rd",
        reminder: false,
      },
      {
        id: 3,
        title: "Farmer's Market",
        day: "April 4th",
        reminder: true,
      },
    ];
  },
};
</script>

<template>
  <div class="container">
    <Header title="Todos" />
    <Todos @toggle-reminder="toggleReminder" @delete-todo="deleteTodo" :todos="todos" />
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppins";
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  padding: 30px;
  border-radius: 2px;
  border: 2px solid crimson;
}
.btn {
  display: inline-block;
  border: 2px solid crimson;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 2px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  background: white;
  font-family: "Poppins";
}
.btn:hover {
  background: crimson;
  color: white;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>

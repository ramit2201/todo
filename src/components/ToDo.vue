<template lang="pug">
    div
      h1 To Do List
    
      input(v-model="newtask" placeholder="Add a new task")
      button(@click="addTask") Add Task
    
      p(v-if="todos.length === 0") No tasks available
    
      ul
        li(v-for="(task, index) in todos" :key="index")
          | {{ task }}
          button(@click="removeTask(index)") Remove
    </template>
    
    <script>
    export default {
      data() {
        return {
          newtask: '',
          todos: []
        };
      },
      methods: {
        addTask() {
          if (this.newtask.trim() !== '') {
            this.todos.push(this.newtask);
            this.newtask = '';
          }
        },
        removeTask(index) {
          this.todos.splice(index, 1);
        }
      }
    };
    </script>
<style scoped>
div {
  max-width: 400px;
  margin: 2rem auto;
  padding: 1rem;
  background-color: #f4f4f4;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  color: #333;
  margin-bottom: 1rem;
}

input {
  width: calc(100% - 100px);
  padding: 0.5rem;
  margin-right: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  padding: 0.5rem 0.75rem;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #369f6e;
}

ul {
  list-style: none;
  padding: 0;
  margin-top: 1rem;
}

li {
  background-color: white;
  margin-bottom: 0.5rem;
  padding: 0.5rem;
  border-radius: 4px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: black;
}

li button {
  background-color: #ff5c5c;
}

li button:hover {
  background-color: #e04a4a;
}

p {
  text-align: center;
  color: #777;
  font-style: italic;
  margin-top: 1rem;
}
</style>
    
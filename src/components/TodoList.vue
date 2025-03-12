<template>
  <div class="todo-list">
    <h2>待办事项列表</h2>
    <div class="add-todo">
      <input 
        v-model="newTodo" 
        @keyup.enter="addTodo" 
        placeholder="添加新的待办事项" 
      />
      <button @click="addTodo">添加</button>
    </div>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        <input 
          type="checkbox" 
          v-model="todo.completed" 
        />
        <span :class="{ completed: todo.completed }">{{ todo.text }}</span>
        <button @click="removeTodo(index)">删除</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  data() {
    return {
      newTodo: '',
      todos: [
        { text: '学习 Vue', completed: false },
        { text: '创建一个项目', completed: false },
        { text: '部署应用', completed: false }
      ]
    }
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim()) {
        this.todos.push({ text: this.newTodo, completed: false });
        this.newTodo = '';
      }
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    }
  }
}
</script>

<style scoped>
.todo-list {
  margin: 20px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
.add-todo {
  margin-bottom: 10px;
}
input[type="text"] {
  padding: 5px;
  width: 60%;
  margin-right: 5px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: flex;
  align-items: center;
  padding: 5px 0;
}
.completed {
  text-decoration: line-through;
  color: #888;
}
button {
  margin-left: 5px;
  padding: 3px 8px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}
button:hover {
  background-color: #45a049;
}
</style>
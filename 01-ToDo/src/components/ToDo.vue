<script>
export default {
  name: 'ToDo',
  data() {
    return {
      tasks: [],
      newTask: '',
    }
  },
  methods: {
    taskDone(task) {
      task.done = !task.done
    },
    addTask() {
      const task = {
        id: Date.now(),
        name: this.newTask,
        done: false
      }
      this.tasks.push(task)
      this.newTask = ''
    },
    deleteTask(task) {
      this.tasks = this.tasks.filter(t => t.id !== task.id)
    },
    saveTasks() {
      localStorage.setItem('tasks', JSON.stringify(this.tasks))
    },
    loadTasks() {
      const storedTasks = localStorage.getItem('tasks')
      if (storedTasks) {
        this.tasks = JSON.parse(storedTasks)
      }
    }
  },
  mounted() {
    this.loadTasks()
  },
  watch: {
    tasks: {
      handler() {
        this.saveTasks()
      },
      deep: true
    }
  }
}

</script>

<template>
  <h1>ToDo App</h1>
  <form @submit.prevent="addTask">
    <input v-model="newTask" type="text" placeholder="Enter a new task">
    <button type="submit">Add Task</button>
  </form>
  <ul class="taskList">
    <li v-for="task in tasks" :key="task.id" class="task">
      <input @click="taskDone(task)" type="checkbox" :checked="task.done">
      <p :class="{complete : task.done}">{{ task.name }}</p>
      <button @click="deleteTask(task)" class="deleteBtn">Delete</button>
    </li>
  </ul>
</template>

<style>
body {
  display: grid;
  place-items: center;
  text-align: center;
}

form {
  display: flex;
  gap: 2px;
}

.task {
  display: flex;
  align-items: center;
  justify-content: space-around;
}

.complete {
  text-decoration: line-through;
  color: gray;
}

.deleteBtn {
  font-weight: 500;
  background: #E4080A;
}

.deleteBtn:hover {
  background: #D20103;
}
</style>
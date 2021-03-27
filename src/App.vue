<template>
  <div class="container">
    <Header @toggle-add-task="toggleAddTask" title="Task Tracker" :showAddTask="showAddTask" />
    <div v-if="showAddTask">
      <AddTask @add-task="addTask" />
    </div>
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks" />
    <h3>{{tasks.length == 0 ? 'No new reminders' : '' }}</h3>
  </div>
</template>

<script>
import Header from "./components/Header";
import Tasks from "./components/Tasks";
import AddTask from "./components/AddTask";
export default {
  name: "App",
  components: {
    Header,
    Tasks,
    AddTask
  },
  data() {
    return {
      tasks: [],
      showAddTask: false
    };
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },
    addTask(task) {
      this.tasks = [...this.tasks, task];
    },
    deleteTask(id) {
      this.tasks = this.tasks.filter(task => task.id !== id);
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map(task =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Task 1",
        day: "Monday",
        reminder: false,
        warning: "Are you sure?",
        active: true
      },
      {
        id: 2,
        text: "Task 2",
        day: "Tuesday",
        reminder: false,
        warning: "Are you sure?",
        active: false
      },
      {
        id: 3,
        text: "Task 3",
        day: "Wednesday",
        reminder: false,
        warning: "Are you sure?",
        active: false
      }
    ];
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  padding: 12px;
  border: 1px solid #ccc;
}

.container {
  max-width: 960px;
  margin-left: auto;
  margin-right: auto;
}
h3 {
  margin: 0;
}
p {
  margin: 0;
}
</style>

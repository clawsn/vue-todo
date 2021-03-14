<template>
  <div class="container">
    <Header title="Tast Tracker" />
    <Tasks :tasks="tasks" />
    <!-- <p>this is sub heading</p> -->
  </div>
</template>

<script>
import Header from "./components/Header";
import Tasks from "./components/Tasks";
export default {
  name: "App",
  components: {
    Header,
    Tasks
  },
  data() {
    return {
      tasks: []
    };
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Task 1",
        day: "Monday",
        reminder: true
      },
      {
        id: 2,
        text: "Task 2",
        day: "Tuesday",
        reminder: true
      },
      {
        id: 3,
        text: "Task 3",
        day: "Wednesday",
        reminder: false
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

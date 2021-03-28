<template>
  <div class="container">
    <Header
      @toggle-add-task="toggleAddTask"
      title="Task Tracker"
      :showAddTask="showAddTask"
    />

    <router-view :showAddTask="showAddTask"></router-view>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";

import Footer from "./components/Footer";
export default {
  name: "App",
  components: {
    Header,
    Footer
  },
  data() {
    return {
      showAddTask: false
    };
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    }
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

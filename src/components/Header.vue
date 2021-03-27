<template>
  <header>
    <h1>{{title}}</h1>
    <Button
      @btn-click="$emit('toggle-add-task')"
      :title="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
    />
  </header>
</template>

<script>
import Button from "./Button";
export default {
  name: "Header",
  props: {
    title: String,
    showAddTask: Boolean
  },
  components: {
    Button
  }
};
</script>

<style scope>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
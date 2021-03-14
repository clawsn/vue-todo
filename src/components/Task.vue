<template>
  <div :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>
      {{ task.text }}
      <i class="fas fa-times"></i>
    </h3>
    <p>{{task.day}}</p>
  </div>
</template>
<script>
export default {
  name: "Task",
  props: {
    task: Object
  }
};
</script>

<style scope>
.fas {
  color: red;
}
.task {
  background-color: #f4f4f4;
  margin: 16px 6px;
  padding: 10px 20px;
  border-radius: 4px;
  transition: 0.2s all ease-out;
  border: 1px solid #ccc;
}
.task:hover {
  box-shadow: 0px -2px 16px rgba(23, 34, 34, 0.2);
  transform: translateY(-3px);
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
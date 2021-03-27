<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="['task', (task.reminder ? 'reminder' : ''), (active ? 'active' : '')]"
  >
    <h3>
      <span>{{ task.text }}</span>
      <span v-if="!active">
        <i @click="active = !active" class="fas fa-times"></i>
      </span>
      <span v-else>
        <i @click="active = !active" class="fas fa-times"></i>
        <i @click="$emit('delete-task', task.id)" class="fas fa-check"></i>
      </span>
    </h3>
    <p>{{task.day}}</p>
    <div v-if="active" class="warning">
      <h2>{{ task.warning }}</h2>
    </div>
  </div>
</template>
<script>
export default {
  name: "Task",
  props: {
    task: Object
  },
  data() {
    return {
      active: false
    };
  }
};
</script>

<style scope>
.fas,
.fa-times,
.fa-check {
  position: relative;
  z-index: 99;
  cursor: pointer;
}
.fa-times {
  color: red;
}

.fa-check {
  color: green;
  padding-left: 6px;
}
.task {
  position: relative;
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
.warning {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(244, 244, 244, 0.9);
}
.warning h2 {
  position: relative;
}
</style>
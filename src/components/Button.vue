<template>
  <button @click="onClick()" class="btn" :style="{background: color}">{{title}}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    title: String,
    color: String
  },
  methods: {
    onClick() {
      console.log("clicked?");
    }
  }
};
</script>

<style scopred>
.btn {
  background-color: #222;
  color: #fff;
  padding: 0.5em 0.8em;
  cursor: pointer;
  border-radius: 4px;
  border: none;
  font-size: 16px;
}
</style>
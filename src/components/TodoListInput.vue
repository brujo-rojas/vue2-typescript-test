<template>
  <div>
    <input type="" v-model="taskEditable.description" />
    <button @click="add">+</button>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import { Task } from "@/types/Task";

@Component
export default class TodoListItem extends Vue {
  taskEditable: Task = { isDone: false, description: "" };
  add(): void {
    this.$emit("add", { ...this.taskEditable });
    this.taskEditable.description = "";
  }
}
</script>

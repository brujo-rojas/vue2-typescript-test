<template>
  <div class="todo-list-item">
    {{ task.description }}
  </div>
</template>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import { Task } from "@/types/Task";

@Component
export default class TodoListItem extends Vue {
  @Prop() private task!: Task;
}
</script>

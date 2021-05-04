<template>
  <div class="todo-list">
    <todo-list-item
      :task="task"
      v-for="(task, index) in tasks"
      :key="index"
    ></todo-list-item>
    <todo-list-input @add="add"></todo-list-input>
  </div>
</template>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import TodoListItem from "@/components/TodoListItem.vue";
import TodoListInput from "@/components/TodoListInput.vue";
import { Task } from "@/types/Task";

@Component({
  components: {
    TodoListItem,
    TodoListInput,
  },
})
export default class TodoList extends Vue {
  @Prop({ type: Array, required: true })
  tasks!: Task[];

  add(task: Task): void {
    this.tasks.push(task);
  }
}
</script>

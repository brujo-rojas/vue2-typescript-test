<template>
  <div class="todo">
    <todo-list :tasks="tasks"> </todo-list>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import TodoList from "@/components/TodoList.vue"; // @ is an alias to /src
import { Task } from "@/types/Task";

@Component({
  components: {
    TodoList,
  },
})
export default class Home extends Vue {
  tasks: Task[] = [
    {
      isDone: false,
      description: "test test test",
    },
    {
      isDone: false,
      description: "test test test",
    },
    {
      isDone: false,
      description: "test test test",
    },
  ];
}
</script>

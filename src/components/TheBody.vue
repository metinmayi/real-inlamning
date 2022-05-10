<template>
  <div>
    <TaskContainer @clickTask="changeTaskStatus" :tasks="unfinished"
      >Unfinished</TaskContainer
    >
    <TaskContainer @clickTask="changeTaskStatus" :tasks="completed"
      >Completed</TaskContainer
    >
  </div>
</template>

<script lang="ts">
import { Vue, Options } from "vue-class-component";
import TaskContainer from "./TaskContainer.vue";
import { Task } from "../models/Task";

@Options({
  components: {
    TaskContainer,
  },
})
export default class TheBody extends Vue {
  unfinished: Task[] = [];
  completed: Task[] = [];
}
</script>

<style lang="scss" scoped>
.div {
  width: 100%;
  gap: 5%;
  display: flex;
  justify-content: center;
}
</style>

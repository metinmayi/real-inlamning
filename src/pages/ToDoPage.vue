<template>
  <TheHeader @submitForm="addNewTask($event)" />
  <div class="wrapper">
    <TaskContainer @clickTask="changeTaskStatus" :tasks="unfinished"
      >Unfinished</TaskContainer
    >
    <TaskContainer @clickTask="changeTaskStatus" :tasks="completed"
      >Completed</TaskContainer
    >
  </div>
</template>

<script lang="ts">
import TaskContainer from "@/components/TaskContainer.vue";
import TheHeader from "@/components/TheHeader.vue";
import { Vue, Options } from "vue-class-component";
import { Task } from "../models/Task";

@Options({
  components: {
    TheHeader,
    TaskContainer,
  },
})
export default class ToDoPage extends Vue {
  unfinished: Task[] = [];
  completed: Task[] = [];

  addNewTask(taskName: string) {
    const task = new Task(taskName, false);
    this.unfinished.push(task);
  }

  changeTaskStatus(task: Task, index: number) {
    let previousArray: Task[];
    let targetedArray: Task[];
    if (task.completed === true) {
      previousArray = this.completed;
      targetedArray = this.unfinished;
    } else {
      previousArray = this.unfinished;
      targetedArray = this.completed;
    }
    task.completed = !task.completed;
    targetedArray.push(task);
    previousArray.splice(index, 1);
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
  width: 100%;
  gap: 5%;
  display: flex;
  justify-content: center;
}
</style>

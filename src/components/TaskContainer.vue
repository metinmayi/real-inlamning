<template>
  <section class="taskWrapper">
    <h1><slot /></h1>
    <div v-if="tasks.length > 0">
      <p
        v-for="(task, index) in tasks"
        v-bind:key="index"
        :class="{ completed: task.completed }"
        @click="clickTask(task, index)"
      >
        {{ task.name }}
      </p>
    </div>
    <div v-else>
      <p>No tasks</p>
    </div>
  </section>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";
import { Task } from "../models/Task";
import { Prop } from "vue-property-decorator";

export default class TaskContainer extends Vue {
  @Prop() tasks!: Task[];

  clickTask(task: Task, index: number) {
    this.$emit("clickTask", task, index);
  }
}
</script>

<style scoped lang="scss">
@use "../assets/styles/styles" as styles;
section {
  color: #c4c4c4;
  text-align: center;
  width: 30%;
  min-height: 10vh;
}
div {
  padding: 3%;
  border: 3px solid #c4c4c4;
  border-radius: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
p {
  cursor: pointer;
}
.completed {
  text-decoration: line-through;
}
</style>

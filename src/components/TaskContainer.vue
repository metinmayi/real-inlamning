<template>
  <div class="taskWrapper">
    <h1><slot /></h1>
    <div class="container">
      <p>Shit</p>
      <p>Shit</p>
      <p>Shit</p>
      <p>Shit</p>
      <p>Shit</p>
      <p>Shit</p>
      <p>Shit</p>
      <p>Shit</p>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";
export default class TaskContainer extends Vue {}
</script>

<style scoped lang="scss">
@use "../assets/styles/styles" as styles;
.taskWrapper {
  color: white;
  text-align: center;
  width: 30%;
  min-height: 10vh;
}
.container {
  padding: 3%;
  border: 3px solid white;
  border-radius: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>

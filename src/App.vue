<template>
  <TheHeader />
  <div class="wrapper">
    <TaskContainer>Unfinished</TaskContainer>
    <TaskContainer>Completed</TaskContainer>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import TheHeader from "./components/TheHeader.vue";
import TaskContainer from "./components/TaskContainer.vue";

@Options({
  components: {
    TheHeader,
    TaskContainer,
  },
})
export default class App extends Vue {}
</script>

<style lang="scss">
@use "./assets/styles/styles" as styles;
body {
  background-color: styles.$primaryColor;
  margin: 0;
  padding: 0;
}
.wrapper {
  width: 100%;
  gap: 5%;
  display: flex;
  justify-content: center;
}
</style>

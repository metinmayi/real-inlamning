<template>
  <ToDoPage />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import ToDoPage from "./pages/ToDoPage.vue";

@Options({
  components: {
    ToDoPage,
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
</style>

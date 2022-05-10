<template>
  <div>
    <form>
      <DefaultInput placeholder="Insert Item..."></DefaultInput>
      <DefaultButton> Add Item </DefaultButton>
    </form>
  </div>
</template>

<script lang="ts">
import { Vue, Options } from "vue-class-component";
import DefaultButton from "./DefaultButton.vue";
import DefaultInput from "./DefaultInput.vue";

@Options({
  components: {
    DefaultButton,
    DefaultInput,
  },
})
export default class TheHeader extends Vue {}
</script>

<style scoped lang="scss">
@use "../assets/styles/styles" as styles;
form {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1%;
  width: 100%;
  height: 20vh;
}
</style>

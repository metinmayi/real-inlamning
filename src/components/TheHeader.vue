<template>
  <form @submit.prevent="submitForm($event)">
    <DefaultInput name="input" placeholder="Insert Item..."></DefaultInput>
    <DefaultButton> Add Item </DefaultButton>
  </form>
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
export default class TheHeader extends Vue {
  value = "";

  submitForm(event: any) {
    if (!event.target.input.value) return;
    this.value = event.target.input.value;
    this.$emit("submitForm", this.value);
    event.target.input.value = "";
  }
}
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

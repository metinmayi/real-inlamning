<template>
  <button type="submit"><slot /></button>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class DefaultButton extends Vue {}
</script>

<style scoped lang="scss">
@use "../assets/styles/styles" as styles;
button {
  display: flex;
  border-radius: 3px;
  width: 5vw;
  height: 4.5vh;
  justify-content: center;
  align-items: center;
  background: transparent;
  color: black;
  background-color: styles.$secondaryColor;
  border: 1px solid white;
  font-family: styles.$primaryFamily;
  cursor: pointer;
}
</style>

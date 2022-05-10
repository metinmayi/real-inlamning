<template>
  <input type="text" />
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class DefaultInput extends Vue {}
</script>

<style scoped lang="scss">
@use "../assets/styles/styles" as styles;
input {
  display: flex;
  border-radius: 3px;
  width: 10vw;
  height: 4vh;
  justify-content: center;
  align-items: center;
  background: transparent;
  color: black;
  background-color: styles.$secondaryColor;
  border: 1px solid white;
  font-family: styles.$primaryFamily;
}
</style>

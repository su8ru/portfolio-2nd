<template>
  <span
    class="simple-icon"
    v-html="simpleIcons.get(name).svg"
    :style="{ fill: getColor }"
  ></span>
</template>

<style lang="scss">
.simple-icon {
  svg {
    height: 1.2rem;
    width: 24px;
  }
}
</style>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class SimpleIcons extends Vue {
  @Prop({ required: true })
  readonly name!: string;
  @Prop()
  readonly color?: string;

  readonly simpleIcons = require("simple-icons");

  get getColor() {
    return this.color || "#" + this.simpleIcons.get(this.name).hex;
  }
}
</script>

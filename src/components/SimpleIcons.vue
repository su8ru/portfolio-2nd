<template>
  <span
    class="simple-icon"
    v-html="icon.svg"
    :style="{ fill: getColor }"
  ></span>
</template>

<style lang="scss">
.simple-icon {
  vertical-align: -2.4px;
  svg {
    height: 1.2rem;
    width: 1.6rem;
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

  readonly icon = require("simple-icons/icons/" + this.name);

  get getColor() {
    return this.color || "#" + this.icon.hex;
  }
}
</script>

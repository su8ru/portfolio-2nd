<template>
  <div class="stack-box">
    <div class="box-left" :style="leftColor">
      <div class="content-left">
        <font-awesome-icon :icon="icon" size="2x" class="icon fa-fw" />
        <h2>{{ title }}</h2>
      </div>
    </div>
    <div class="box-right" :style="rightColor">
      <div class="content-right">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.stack-box {
  display: flex;
  flex-direction: row;

  .box-left {
    width: 40%;
    display: flex;
    flex-direction: row-reverse;

    background: var(--color);

    .content-left {
      $width: 400px;
      width: $width;
      max-width: $width;
      padding: 2rem 1rem;

      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-start;

      * {
        display: block;
        color: #666;
      }

      svg {
        margin-left: 30%;
      }

      h2 {
        margin-left: 1rem;
      }
    }
  }

  .box-right {
    width: 60%;
    display: flex;
    flex-direction: row;

    background: rgba(var(--r), var(--g), var(--b), 0.4);

    &:hover {
      background: rgba(var(--r), var(--g), var(--b), 0.5);
    }

    .content-right {
      $width: 600px;
      width: $width;
      max-width: $width;
      padding: 1rem 1rem 1rem 2rem;

      display: block;

      * {
        color: #444;
      }
    }
  }
}
</style>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class StackBox extends Vue {
  @Prop({ required: true })
  readonly icon!: string;
  @Prop({ required: true })
  readonly title!: string;
  @Prop({ required: true })
  readonly color!: string;

  get leftColor() {
    return {
      background: this.color,
    };
  }
  get rightColor() {
    return {
      "--r": this.rgbColor.r,
      "--g": this.rgbColor.g,
      "--b": this.rgbColor.b,
    };
  }

  get rgbColor(): { r: number; g: number; b: number } {
    return {
      r: parseInt(this.color.substr(1, 2), 16),
      g: parseInt(this.color.substr(3, 2), 16),
      b: parseInt(this.color.substr(5, 2), 16),
    };
  }
}
</script>

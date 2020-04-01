<template>
  <div id="home">
    <stack-box color="#c1dfff" title="about" icon="user"></stack-box>
    <stack-box color="#dfffc1" title="being" icon="school"></stack-box>
    <stack-box color="#ffe1c1" title="skill" icon="terminal"></stack-box>
    <stack-box color="#ffc1df" title="contact" icon="envelope"></stack-box>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import StackBox from "@/components/StackBox.vue";

@Component({
  components: {
    StackBox,
  },
})
export default class Home extends Vue {}
</script>

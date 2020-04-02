<template>
  <div id="home">
    <div id="top">
      <img id="icon" src="https://gravatar.su8ru.dev?s=200" alt="icon" />
      <div id="name">
        <h1><img :src="logo" alt="すばる" width="300" /></h1>
        <h2>su8ru</h2>
      </div>
    </div>
    <stack-box color="#c1dfff" title="about" icon="user">
      <table>
        <tbody>
          <tr>
            <th>
              <h3>
                <font-awesome-icon icon="birthday-cake" class="fa-fw" />
                birthday
              </h3>
            </th>
            <td>2003.08.09</td>
          </tr>
          <tr>
            <th>
              <h3>
                <font-awesome-icon icon="address-card" class="fa-fw" />
                being
              </h3>
            </th>
            <td>
              Azabu High School<br />
              73rd AFes Executive Committee
            </td>
          </tr>
          <tr>
            <th>
              <h3>
                <font-awesome-icon icon="map-marker-alt" class="fa-fw" />
                live
              </h3>
            </th>
            <td>
              Tokyo, Japan
            </td>
          </tr>
        </tbody>
      </table>
    </stack-box>
    <stack-box color="#dfffc1" title="skill" icon="terminal"></stack-box>
    <stack-box color="#ffe1c1" title="work" icon="folder"></stack-box>
    <stack-box color="#ffc1df" title="contact" icon="envelope"></stack-box>
  </div>
</template>

<style lang="scss" scoped>
#home {
  #top {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;

    background: #fefefe;

    #icon {
      margin: 1rem;
    }

    #name {
      display: flex;
      flex-direction: column;
      align-items: center;

      h1,
      h2 {
        display: block;
        width: max-content;
      }

      h2 {
        color: #666;
        font-size: 2rem;
      }
    }
  }
}
</style>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import StackBox from "@/components/StackBox.vue";

@Component({
  components: {
    StackBox,
  },
})
export default class Home extends Vue {
  readonly logo = require("../assets/logo.svg");
}
</script>

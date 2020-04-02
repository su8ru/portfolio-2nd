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
    <stack-box color="#dfffc1" title="skill" icon="terminal">
      <table>
        <tbody>
          <tr>
            <th>
              <h3>
                <simple-icons name="html5" />
                HTML5
              </h3>
            </th>
          </tr>
          <tr>
            <th>
              <h3>
                <simple-icons name="css3" />
                CSS3
              </h3>
            </th>
            <td>
              <ul>
                <li>
                  <simple-icons name="sass" />
                  Sass
                </li>
                <li>
                  <simple-icons name="bootstrap" />
                  Bootstrap
                </li>
              </ul>
            </td>
          </tr>
          <tr>
            <th>
              <h3>
                <simple-icons name="typescript" />
                TypeScript
              </h3>
            </th>
          </tr>
          <tr>
            <th>
              <h3>
                <simple-icons name="php" />
                PHP
              </h3>
            </th>
          </tr>
          <tr>
            <th>
              <h3>
                <simple-icons name="vue-dot-js" />
                Vue.js
              </h3>
            </th>
          </tr>
          <tr>
            <th>
              <h3>
                <simple-icons name="cplusplus" />
                C++
              </h3>
            </th>
            <td>
              <ul>
                <li>
                  <simple-icons name="visualstudio" />
                  Visual Studio
                </li>
              </ul>
            </td>
          </tr>
          <tr>
            <th>
              <h3>
                <simple-icons name="git" />
                Git
              </h3>
            </th>
            <td>
              <ul>
                <li>
                  <simple-icons name="github" />
                  GitHub
                </li>
                <li>
                  <simple-icons name="githubactions" />
                  GitHub Actions
                </li>
                <li>
                  <simple-icons name="gitkraken" />
                  GitKraken
                </li>
              </ul>
            </td>
          </tr>
          <tr>
            <th>
              <h3>
                <simple-icons name="adobeillustrator" />
                Illustrator
              </h3>
            </th>
            <td>
              <ul>
                <li>
                  <simple-icons name="svg" />
                  SVG
                </li>
              </ul>
            </td>
          </tr>
          <tr>
            <th>
              <h3>
                <simple-icons name="jetbrains" />
                JetBrains
              </h3>
            </th>
          </tr>
        </tbody>
      </table>
    </stack-box>
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
import SimpleIcons from "@/components/SimpleIcons.vue";

@Component({
  components: {
    StackBox,
    SimpleIcons,
  },
})
export default class Home extends Vue {
  readonly logo = require("../assets/logo.svg");
}
</script>

<template>
  <div id="home">
    <div id="top">
      <img id="icon" src="https://gravatar.su8ru.dev?s=200" alt="icon" />
      <div id="name">
        <h1><img :src="logo" alt="すばる" width="250" /></h1>
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
    <stack-box color="#ffe1c1" title="work" icon="folder">
      <table>
        <tbody>
          <tr v-for="work in works" :key="work.title">
            <td>
              <carousel
                :per-page="1"
                :pagination-enabled="false"
                :navigation-enabled="false"
                :autoplay="true"
                :loop="true"
                :speed="1000"
                :autoplay-timeout="5000"
                class="work-carousel"
              >
                <slide v-for="img in work.img" :key="img">
                  <img :src="img" alt="work img" class="s-img" />
                </slide>
              </carousel>
            </td>
            <td>
              {{ work.title }}
              <span v-if="work.skills">
                <br />
                <simple-icons
                  v-for="skill in work.skills"
                  :key="skill"
                  :name="skill"
                />
              </span>
              <a v-if="work.url" :href="work.url" target="_blank">
                <br />{{ work.url }}
              </a>
              <a
                v-if="work.github"
                :href="'https://github.com/' + work.github"
                target="_blank"
              >
                <br />
                <simple-icons name="github" />
                {{ work.github }}
              </a>
            </td>
          </tr>
        </tbody>
      </table>
    </stack-box>
    <stack-box color="#ffc1df" title="contact" icon="envelope">
      <ul class="list-row">
        <li>
          <a href="https://twitter.com/su8ru_" target="_blank">
            <font-awesome-icon :icon="['fab', 'twitter']" class="fa-fw fa-2x" />
          </a>
        </li>
        <li>
          <a href="https://github.com/su8ru" target="_blank">
            <font-awesome-icon :icon="['fab', 'github']" class="fa-fw fa-2x" />
          </a>
        </li>
        <li>
          <a href="mailto:contact@su8ru.dev" target="_blank">
            <font-awesome-icon icon="envelope" class="fa-fw fa-2x" />
          </a>
        </li>
      </ul>
    </stack-box>
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

    @media screen and (max-width: 1000px) {
      #icon {
        width: 30%;
        margin: 0.5rem;
      }
      #name {
        width: calc(70% - 3rem);
        margin: 0.5rem 1.5rem 0.5rem 0.5rem;

        h1,
        img {
          max-width: 100%;
          width: 100%;
        }
      }
    }
  }
}
</style>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import StackBox from "@/components/StackBox.vue";
import SimpleIcons from "@/components/SimpleIcons.vue";
import { Carousel, Slide } from "vue-carousel";

@Component({
  components: {
    StackBox,
    SimpleIcons,
    Carousel,
    Slide,
  },
})
export default class Home extends Vue {
  readonly logo = require("../assets/logo.svg");
  readonly works = {
    afes: {
      img: [require("../assets/work/afes.png")],
      title: "73rd AFes Website",
      url: "https://afes.info",
      github: "afes-website",
      skills: [
        "vue-dot-js",
        "typescript",
        "html5",
        "css3",
        "sass",
        "bootstrap",
        "php",
        "git",
        "github",
        "githubactions",
      ],
    },
    kostl: {
      img: [
        require("../assets/work/kostl1.png"),
        require("../assets/work/kostl2.png"),
        require("../assets/work/kostl3.png"),
        require("../assets/work/kostl4.png"),
      ],
      title: "こすとれ - KO･S Train Location",
      url: "https://kostl.info",
      github: "su8ru/kostl",
      skills: [
        "vue-dot-js",
        "typescript",
        "html5",
        "css3",
        "sass",
        "git",
        "github",
        "githubactions",
      ],
    },
    sw2: {
      img: [
        require("../assets/work/sw21.png"),
        require("../assets/work/sw22.png"),
      ],
      title: "Space Wars 2",
      github: "apcc/SpaceWars2",
      skills: ["cplusplus", "visualstudio"],
    },
  };
}
</script>

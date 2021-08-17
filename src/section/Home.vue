<template>
  <div class="hello">

    <Header />
    <h2 id="propos" class="titlesection">À Propos</h2>
    <div class="divider"></div>
    <section class="apropos">

      <div class="titlehome items">
        <h3>Nina Toinon</h3>
        <p>Developper web </p>
        <div class="presentation">
          <p>
            Bonjour, Je suis anciennement diplomée d'un CAP vente et d'une certification d'agent de montage cablage en électronique.
            J'ai souhaiter me réorienter dans un domaine qui me plait davantage et dans lequel je m'était déja plonger par simple loisir : Le développement web . <br />
            autodidacte, j'ai commencé par apprendre l'utilisation de photoshop, et de la création de photomontage, puis au fur et a mesure je me suis tourné vers la customisation via le codage.
            j'ai réalisé pour un groupe d'écriture auquel je faisait partie un site internet de présentation.
            J'ai décider d'allier mon loisir dans le domaine professionnel et pour cela j'ai fait une formation de dévellopeuse web chez openclassrooms. Sur ce portfolio voici mes réalisations .
            Je suis une personne motivée, patiente, avec une capacité d'adaptation, d'autonomie et capable de travailler en équipe.
          </p><br />
          <a href="https://drive.google.com/file/d/1ThiIFKdhzAgaQP_vrHg0aTVJD7MDuunV/view?usp=sharing" download>Télécharger mon CV</a>
        </div>
      </div>
      <div class="devphoto items">
        <img class="logo" src="../assets/designer-photo.jpg" alt="" />
      </div>
    </section>
    <h2 class="titlesection">Compétences</h2>
    <div class="divider"></div>
    <section class="competences">
      <p> Un rapide aperçu des compétences acquises au cours de ma formation</p>
      <div class="svgcompétences">
        <img class="logocompétence" src="../assets/competences/html5-svgrepo-com.svg" alt="" />
        <img class="logocompétence" src="../assets/competences/css.svg" alt="" />
        <img class="logocompétence" src="../assets/competences/javascript-seeklogo.com.svg" alt="" />
        <img class="logocompétence" src="../assets/competences/sass-lang-ar21.svg" alt="" />
        <br />
        <button class="voirplus" v-on:click="show = !show">
          Voir Plus
        </button>
        <transition name="fade">
          <div v-if="show">
            <competences />
          </div>
        </transition>
      </div>
    </section>
    <h2 id="projets" class="titlesection">Projets</h2>
    <div class="divider"></div>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>

  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Competences from "@/components/Competences.vue";

export default {
  name: "Home",
  components: {
    Header,
    Competences,
  },
  data() {
    return {
      show: false,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  margin: 30px 10px 10px 10px;
  background: url(../assets/body-bg.png);
  padding: 10px;
}
.divider {
  margin: 0 0 30px 0;
  width: 100%;
  height: 2px;
  background: url(../assets/divider.png) repeat-x;
  clear: both;
}

.titlesection {
  text-align: left;
  margin-bottom: 0;
  font: 400 28px/50px "Bree Serif", Georgia, serif;
}
.apropos {
  padding-top: 30px;
  padding-bottom: 30px;
  display: flex;
  flex-direction: column-reverse;
}

.titlehome p,
h3 {
  margin: auto 0 0 0;
}
.titlehome h3 {
  margin: auto 0 0 0;
  font-weight: 400;
  font-size: 30px;
}
.presentation {
  padding-top: 30px;
  font-size: 16px;
  line-height: 2;
}
.presentation p {
  text-align: justify;
}
img {
  width: 50%;
}

h3 {
  margin: 20px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #729fcf;
}
.logocompétence {
  width: 50px;
  margin: 10px 10px 10px 10px;
}
.voirplus {
  margin: 15px;
  padding: 10px;
  border-radius: 10px;
  background-color: #729fcf;
  font-weight: 600;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

@media (min-width: 1024px) {
  .hello {
    margin: 30px;
    padding: 30px;
  }
  .apropos {
    flex-direction: row;
  }
  img {
    width: auto;
  }

  .titlehome h3 {
    font-size: 46px;
  }
  .presentation {
    padding: 30px;
    font-size: 16px;
  }
  .logocompétence {
    width: 100px;
  }
}
</style>
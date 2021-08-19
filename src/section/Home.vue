<template>
  <div>

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
          <a href="https://drive.google.com/file/d/1ThiIFKdhzAgaQP_vrHg0aTVJD7MDuunV/view?usp=sharing" target="_blanck" download>Télécharger mon CV</a>
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


<style scoped>
/*------------------------------Home--------------------------*/
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

@media (min-width: 1024px) {
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
<template>
  <div>
    <h2 id="projets" class="titlesection">Projets</h2>
    <div class="divider"></div>
    <div class="work-container">
      <ul class="criteria-list">
        <li v-for="item in criteria" :key="item">
          <FilterTags v-on:clicked="criteriaSeletion" :type="item" :state="selectedType === item" />
        </li>
      </ul>
      <div class="container-flex">
        <div class="project-holder" v-for="project in filterProject" :key="project.index">
          <ProjectModule v-on:emitImage="imagePreview" :title="Object.keys(project).toString()" :preview="project[Object.keys(project).toString()].preview_links" :type="project[Object.keys(project).toString()].category" :read="project[Object.keys(project).toString()].article" :coverImage="project[Object.keys(project).toString()].image" :content="project[Object.keys(project).toString()].content" class="module" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProjectModule from "../components/ProjectModule";
import FilterTags from "../components/filterTag";
import project from "../ProjectData";
export default {
  name: "Work",
  components: {
    ProjectModule,
    FilterTags,
  },
  data() {
    return {
      selectedType: "Favorites",
      criteria: ["Favorites", "Codage", "Graphic Design"],
    };
  },
  methods: {
    criteriaSeletion(type) {
      this.selectedType = type;
    },
    imagePreview(e) {
      this.$emit("emitImage", e);
    },
  },
  computed: {
    filterProject() {
      return project.filter((pr) => {
        if (this.selectedType === "Favorites") {
          return pr[Object.keys(pr).toString()].favorite === this.selectedType;
        }
        return pr[Object.keys(pr).toString()].category === this.selectedType;
      });
    },
  },
};
</script>
<style scoped>
/*------------------------------Projet affichage--------------------------*/
.project-holder {
  display: flex;
  justify-content: center;
}

.project-container {
  display: flex;
  flex-flow: column nowrap;
  border: 1px solid grey;
  border-radius: 20px;
  margin-bottom: 15px;
  padding: 15px;
  width: 100%;
}
.criteria-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  padding: 0;
}
.criteria-list li {
  list-style: none;
}

.module {
  margin-bottom: 15px;
  transition: box-shadow 0.4s ease-in-out;
}
.module:hover {
  box-shadow: 0 0 10px 10px rgba(0, 0, 0, 0.2);
}

@media (min-width: 930px) {
  .project-container {
    width: 30%;
  }
}

@media (min-width: 1024px) {
  .container-flex {
    display: flex;
    flex-wrap: wrap;
  }

  .project-holder {
    justify-content: space-around;
    flex-wrap: wrap;
    width: 50%;
    flex-direction: column;
    height: fit-content;
  }

  .project-container {
    width: auto;
    margin: 5px;
  }
}
</style>
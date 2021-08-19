<template>
  <article class="project-container">
    <header>
      <div class="title-type">
        <h3>{{  projectName }}</h3>
        <div class="type-meta">{{ type }}</div>
      </div>
      <div class="custom-icons">
        <a v-for="(link, platform) in preview" :key="platform.index" :href="link" target="_blank" rel="noopener">
          <img class="preview-platform-icons filtergrey" :src="require(`../assets/icons/${platform}.svg`)" :alt="`link for ${platform}`" />
        </a>
      </div>
    </header>
    <p class="content" v-if="content">
      {{ content }}
    </p>
    <div class="container-image">
      <img class="cover-image" :src="coverImage" :alt="`Screenshot of ${ projectName}`" @click="emitImage" />
    </div>
    <button v-if="read" @click="readMore" class="more">
      <span v-if="type === 'Graphic Design'">
        Watch
        <svg xmlns="http://www.w3.org/2000/svg" height="18" viewBox="0 0 24 24" width="18">
          <path d="M0 0h24v24H0z" fill="none" />
          <path d="M4.2,0.2v23.6L22.8,12L4.2,0.2z" />
        </svg></span>
      <span v-else> Read More </span>
    </button>
  </article>
</template>

<script>
export default {
  name: "ProjectModule",
  props: {
    title: {
      type: String,
      required: true,
    },
    content: {
      content: {
        type: String,
        required: false,
      },
    },
    preview: {
      type: Object,
      required: true,
    },
    coverImage: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      required: true,
    },
    read: {
      type: String,
      required: false,
    },
  },
  computed: {
    projectName() {
      let projectName = this.title;
      projectName = projectName.charAt(0).toUpperCase() + projectName.slice(1);
      projectName = projectName.replace(/_/g, " ");
      return projectName;
    },
  },
  methods: {
    readMore() {
      window.open(this.read, "_blank", "noopener");
    },
    emitImage() {
      this.$emit("emitImage", this.coverImage);
    },
  },
};
</script>
<style scoped>
/*------------------------------Projet module--------------------------*/
.cover-image {
  margin-top: 20px;
  width: 100%;
  border-radius: 20px;
}
.container-image {
  width: fit-content;
  margin: auto;
}
.preview-platform-icons {
  width: 40px;
  margin: 15px 10px;
}
.title-type {
  display: flex;
  align-items: center;
  flex-flow: column;
  justify-content: space-around;
}
.title-type h3 {
  color: #729fcf;
}
.type-meta {
  background-color: #bdbbbb;
  border-radius: 20px;
  color: black;
  width: 150px;
  padding: 5px;
}

.content {
  text-align: justify;
}

@media (min-width: 768px) {
  .title-type {
    display: flex;
    align-items: center;
    flex-flow: row nowrap;
    justify-content: space-around;
  }
  .cover-image {
    width: 100%;
    border-radius: 20px;
    height: fit-content;
  }
}
</style>
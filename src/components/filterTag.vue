<template>
  <div @click="$emit('clicked', type)" :class="state ? 'type-meta-active' : 'type-meta'">
    {{ type }} <img class="fav" v-if="type === 'Favorites'" src="../assets/icons/star-solid.svg" alt="projets favoris" />
  </div>
</template>

<script>
export default {
  name: "FilterTags",
  props: {
    type: {
      type: String,
      required: true,
    },
    state: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
};
</script>
<style scoped>
.fav {
  width: 15px;
}
</style>
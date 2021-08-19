<template>
  <div @click="$emit('clicked', type)" :class="state ? 'category-active' : 'category-non-active'">
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
.category-active:hover {
  background-color: #3c84d1;
}
.category-non-active {
  background-color: #729fcf;
  cursor: pointer;
  border-radius: 20px;
  margin: 5px 5px 15px 5px;
  color: black;
  padding: 10px;
  font-size: 14px;
  width: 120px;
  font-weight: 600;
}
.category-active {
  background-color: #3c84d1;
  cursor: pointer;
  border-radius: 20px;
  margin: 5px 5px 15px 5px;
  color: black;
  padding: 10px;
  font-size: 14px;
  list-style: none;
  width: 120px;
  font-weight: 600;
}
</style>
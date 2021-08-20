<template>
  <header class="container">
    <span class="text1">" Hello ! " </span>
    <h1 class="text2">Bienvenue sur mon Portfolio</h1>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
* {
  padding: 0;
  margin: auto;
}

.container {
  padding: 20px;
  text-align: center;
  background-color: #282828;
  margin: 0;
}
.container span,
h1 {
  color: #3c84d1;
  text-transform: uppercase;
  display: block;
}
.text1 {
  letter-spacing: 2px;
  margin-bottom: 20px;
  background-color: #282828;
}
.text2 {
  font-size: 15px;
  color: #c7c7c7;
}

@media (min-width: 426px) {
  .text1 {
    font-size: 60px;
    letter-spacing: 8px;
    position: relative;
    animation: text 3s 1 ease;
    background-color: #282828;
  }
  .text2 {
    color: #c7c7c7;
  }
  @keyframes text {
    0% {
      color: #282828;
      margin-bottom: -40px;
    }
    30% {
      letter-spacing: 10px;
      margin-bottom: -40px;
    }
    85% {
      letter-spacing: 8px;
      margin-bottom: -40px;
    }
  }
}
</style>
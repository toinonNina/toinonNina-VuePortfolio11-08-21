<template>
  <h2 id="contact" class="titlesection">Contact</h2>
  <div class="divider"></div>
  <section class="contact">
    <div class="container-contact">
      <div class="icon-contact">
        <a href="mailto:zd.toinon@gmail.com"> <img class="filtergrey" src="../assets/icons/Mail_(iOS).svg" alt="Email" /></a>
      </div>
      <div class="icon-contact">
        <a href="https://www.linkedin.com/in/nina-toinon-17072b200/"> <img class="filtergrey" src="../assets/icons/linkedin-svgrepo-com.svg" alt="Linkedin" /></a>
      </div>
      <div class="icon-contact">
        <a href="https://github.com/toinonNina"> <img class="filtergrey" src="../assets/icons/github.svg" alt="github" /></a>
      </div>
      <div class="icon-contact">
        <a href="https://www.deviantart.com/zazeal"> <img class="filtergrey" src="../assets/icons/deviantart.svg" alt="deviantart" /></a>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "Contact",
};
</script>
<style scoped>
.container-contact {
  display: flex;
  justify-content: space-around;
}
.designer {
  border-radius: 50%;
  width: 50%;
}

.icon-contact img {
  width: 50px;
}
</style>
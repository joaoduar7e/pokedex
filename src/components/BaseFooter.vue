<template>
  <div class="footer">
    <footer>
      <p>Feito por João Paulo V. Duarte</p>

      <img id="logo" src="@/assets/pokemon-logo.png" alt="Logo Pokemon" />
     
      <a target="_blank" href="https://github.com/joaoduar7e"> <b-icon icon="github" scale="2"></b-icon> </a>
      <a target="_blank" href="https://www.linkedin.com/in/joaoduar7e/" > <b-icon icon="linkedin" scale="2"></b-icon> </a>

    </footer>
  </div>
</template>

<script>
export default {
  name: "BaseFooter",
};
</script>

<style scoped>
footer {
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
  max-width: 650px;
  align-items: center; 
  justify-content: space-around 
}

footer > p,
img,
a {
  padding: 10px;
  text-align: center;
  text-decoration: none;
  color: black;
}

footer > p,
a {
  padding-top: 5%;
  text-align: center;
  text-decoration: none;
  color: black;
}

#logo {
  max-width: 20%;
  min-width: 20%;
}
</style>

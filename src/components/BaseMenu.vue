<template>
  <div class="user">
    <div class="menu">
      <img id="logo" src="@/assets/pokemon-logo.png" alt="Logo Pokemon" />
    </div>

    <h2>Pokédex</h2>
  </div>
</template>

<script>
export default {
  name: "BaseMenu",
};
</script>

<style scoped>
#menu {
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
  justify-content: center;
}

#logo {
  max-width: 30%;
  min-width: 30%;
  text-align: center;
}
</style>

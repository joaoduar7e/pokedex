<template>
  <div class="user">
    <BaseMenu />

    <section class="infos">
      <div id="card" class="card">
        <v-col cols="3" v-for="pokemon in pokemons" :key="pokemon.name">
          <div id="poke" class="poke">
            <p>{{ pokemon.name | upperCase }}</p>
            <img
              :src="`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${get_id(
                pokemon
              )}.png`"
              :alt="pokemon.name"
              width="100%"
            />

            <p>{{ pokemon.types }}</p>
          </div>
        </v-col>
      </div>
    </section>

    <BaseFooter />
  </div>
</template>


<script>
import api from "../service/api";
import BaseMenu from "@/components/BaseMenu.vue";
import BaseFooter from "@/components/BaseFooter.vue";

export default {
  name: "PokemonU",
  components: {
    BaseMenu,
    BaseFooter,
  },
  data() {
    return {
      pokemons: [],
    };
  },
  created() {
    this.getPokemon();
  },
  methods: {
    getPokemon() {
      api
        .get("pokemon?limit=151")
        .then((res) => {
          this.pokemons = res.data.results;
        })
        .catch((error) => {
          console.log(error);
        });
    },

    get_id(pokemon) {
      return pokemon.url.split("/")[6];
    },
  },
  filters: {
    upperCase: function (value) {
      var newName = value[0].toUpperCase() + value.slice(1);
      return newName;
    },
  },
};
</script>

<style scoped>
.infos {
  display: grid;
  max-width: 650px;
  margin: 0 auto;
}

.infos > .card {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 10px;
  align-items: center;
  grid-column: auto;
  grid-row: auto;
  border: none;
}

.poke:hover {
  transform: scale(1.1);
  transition: all 0.5s;
}

.poke {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
}
</style>

<template>
  <div className="app">
    <NavBar />
    <CountriesList :paises="countries" />
  </div>
</template>
<script>
import NavBar from "./components/NavBar.vue";
import CountriesList from "./components/CountriesList.vue";
import countries from "./countries.json";

export default {
  components: {
    NavBar,
    CountriesList,
  },
  data() {
    return {
      countries: countries,
    };
  },
};
</script>
<style></style>

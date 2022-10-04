<template>
  <div v-for="pais in country" :key="pais.name.common" class="col-7">
    <img
      :src="
        `https://flagpedia.net/data/flags/icon/72x54/` +
        pais.alpha2Code.toLowerCase() +
        `.png`
      "
      alt="country flag"
      style="width: 150px"
    />
    <h1>{{ pais.name.common }}</h1>
    <table class="table">
      <thead></thead>
      <tbody>
        <tr>
          <td style="width: 30%">Capital</td>
          <td>{{ pais.capital[0] }}</td>
        </tr>
        <tr>
          <td>Area</td>
          <td>Los km de la ciudad {{ pais.area }}km <sup>2</sup></td>
        </tr>
        <tr>
          <td>Borders</td>
          <td>
            <ul>
              <li v-for="borders in pais.borders" :key="borders">
                <router-link :to="`/details/` + borders">{{
                  borders
                }}</router-link>
              </li>
            </ul>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import countries from "../countries.json";
export default {
  data() {
    return {
      ListOfCountries: countries,
      country: [],
    };
  },
  methods: {
    getCountry(ruta) {
      const alpha2code = ruta;
      this.country = this.ListOfCountries.filter(
        (pais) => pais.alpha2Code === alpha2code
      );
    },
  },
  updated() {
    this.getCountry(this.$route.params.alpha2code);
  },
  mounted() {
    this.getCountry(this.$route.params.alpha2code);
  },
};
</script>

<style></style>

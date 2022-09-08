<template>
  <div class="container">
    <div class="row">
      <div class="col-5" style="max-height: 90vh; overflow: scroll">
        <div class="list-group">
          <router-link
            class="list-group-item list-group-item-action"
            v-for="pais in paises"
            :key="pais.name"
            to="/details"
          >
            <img
              :src="
                `https://flagpedia.net/data/flags/icon/72x54/` +
                pais.alpha2Code.toLowerCase() +
                `.png`
              "
            />
            <p>{{ pais.name.common }}</p>
          </router-link>
        </div>
      </div>
      <router-view />
    </div>
  </div>
</template>

<script>
export default {
  props: ["paises"],
};
</script>

<style></style>

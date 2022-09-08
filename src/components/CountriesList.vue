<template>
  <div class="container">
    <div class="row">
      <div class="col-5" style="max-height: 90vh; overflow: scroll">
        <div class="list-group">
          <a
            class="list-group-item list-group-item-action"
            v-for="pais in paises"
            :key="pais.name"
            href=""
          >
            <img
              :src="
                `https://flagpedia.net/data/flags/icon/72x54/` +
                pais.alpha2Code.toLowerCase() +
                `.png`
              "
            />
          </a>
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

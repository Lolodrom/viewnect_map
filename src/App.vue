<template>
  <div>
    <mj-map/>
  </div>
</template>

<script>
import MjMap from "./components/Map.vue";
import AS from "algoliasearch/lite";
import {
  AisInstantSearch,
  AisHits,
  AisHighlight,
  AisConfigure
} from "vue-instantsearch";

const SO_API_KEY = "32a8a39590baeef338affc3e94bf4b5d";
const APP_ID = "9HNPCPAVXC";
const INDEX_NAME = "viewnect";

const algoliaclient = AS(APP_ID, SO_API_KEY);
//const index = algoliaclient.initIndex('INDEX_NAME');

export default {
  components: {
    MjMap,
    AS
  }
};
</script>

<style>
</style>
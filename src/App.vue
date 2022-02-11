<template>
  <div class="generic-container d-flex flex-column">
    <Header @change="changeSearch" :genres="genres" :titles="titles" />
    <Main :discs="discs" :search="search" />
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data() {
    return {
      discs: [],
      search: "",
      genres: [],
      titles: [],
    };
  },
  methods: {
    changeSearch(value) {
      this.search = value;
    },
    pushInArray(nameArray, elementToPush) {
      if (!nameArray.includes(elementToPush)) {
        nameArray.push(elementToPush);
      }
    },
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.discs = res.data.response;
        for (let i = 0; i < this.discs.length; i++) {
          const { genre, title } = this.discs[i];
          this.pushInArray(this.genres, genre);
          this.pushInArray(this.titles, title);
        }
      });
  },
};
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>

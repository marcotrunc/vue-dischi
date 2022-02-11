<template>
  <header>
    <div class="container-fluid">
      <div class="row align-items-center">
        <div class="col-2">
          <figure class="p-2">
            <img
              src="../assets/img/logo-spotify.png"
              alt="logo-spotify"
              class="img-fluid"
            />
          </figure>
        </div>
        <div class="offset-8 col-2">
          <Select @changes="changeSearch" :genres="genres" :titles="titles" />
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import Select from "./Select.vue";
export default {
  name: "Header",
  props: ["genres", "titles"],
  components: {
    Select,
  },
  methods: {
    changeSearch(value) {
      const search = value;
      this.$emit("change", search);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/_variables.scss";

header {
  background-color: $bg-grey;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1;
  figure {
    width: 71px;
    margin: 0;
  }
}
</style>
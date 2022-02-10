<template>
  <main>
    <div class="container">
      <div class="row gy-5 gx-md-5">
        <div
          id="col"
          v-for="(disc, index) in discs"
          :key="index"
          class="col-6 col-md-3 col-lg-3"
        >
          <Card
            :poster="disc.poster"
            :author="disc.author"
            :title="disc.title"
            :year="disc.year"
          />
        </div>
      </div>
    </div>
  </main>
</template>
<script>
import axios from "axios";
import Card from "./Card.vue";
export default {
  name: "Main",
  components: {
    Card,
  },
  data() {
    return {
      discs: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.discs = res.data.response;
      });
  },
};
</script>
<style lang="scss" scoped>
@import "../assets/scss/_variables.scss";
main {
  background-color: $bg-blue;
  padding-top: 130px;
  padding-bottom: 20px;
}
@media screen and (min-width: 992px) {
  #col {
    width: 20%;
  }
}
</style>
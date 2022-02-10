<template>
  <div>
    <section id="cards" class="disc-card text-light">
      <figure>
        <img :src="poster" :alt="author" class="img-fluid" />
      </figure>
      <div
        class="
          description
          d-flex
          flex-column
          justify-content-center
          text-center
        "
      >
        <h4 class="text-uppercase">{{ title }}</h4>
        <span class="year">{{ year }}</span>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["poster", "author", "title", "year"],
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/_variables.scss";
#cards {
  background-color: $bg-grey;
  padding: 1rem;
}
.disc-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 300px;
}
h4 {
  font-size: 1.2em;
}

@media screen and (max-width: 400px) {
  .disc-card {
    height: 200px;
  }
  h4 {
    font-size: 0.6em;
  }
  .year {
    font-size: 0.6em;
  }
}
@media screen and (max-width: 260px) {
  #cards {
    padding: 0;
    padding-bottom: 5px;
  }
  .disc-card {
    height: auto;
  }
  h4 {
    font-size: 0.6em;
  }
  .year {
    font-size: 0.6em;
  }
}
</style>
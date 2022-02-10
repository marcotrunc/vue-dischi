<template>
  <header>
    <div class="container-fluid">
      <div class="row">
        <div class="col-2">
          <figure class="p-2">
            <img
              src="../assets/img/logo-spotify.png"
              alt="logo-spotify"
              class="img-fluid"
            />
          </figure>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
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
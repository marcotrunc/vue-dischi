<template>
  <div>
    <label for="search-for-anything" class="me-2 text-white"
      >Ricerca per Titolo</label
    >
    <select
      name="search-for-anything"
      id="search-for-anything"
      v-model="search"
      @change="$emit('changes-title', search)"
    >
      <option value="">---</option>
      <option v-for="(title, index) in titles" :key="index" :value="title">
        {{ title }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Selectedtitle",
  props: ["titles"],
  data() {
    return {
      search: "",
    };
  },
};
</script>

<style lang="scss" scoped>
</style>
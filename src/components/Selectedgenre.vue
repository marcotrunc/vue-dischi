<template>
  <div>
    <label for="search-for-anything" class="me-2 text-white"
      >Ricerca per genere</label
    >
    <select
      name="search-for-anything"
      id="search-for-anything"
      v-model="search"
      @change="$emit('changes', search)"
    >
      <option value="">---</option>
      <option v-for="(genre, index) in genres" :key="index" :value="genre">
        {{ genre }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Selectedgenre",
  props: ["genres"],
  data() {
    return {
      search: "",
    };
  },
};
</script>

<style lang="scss" scoped>
</style>
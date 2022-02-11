<template>
  <div>
    <select
      name="search-for-anything"
      id="search-for-anything"
      v-model="search"
      @change="$emit('changes', search)"
    >
      <option value="Rock">Rock</option>
      <option value="Rap">Rap</option>
      <option value="Pop">Pop</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Select",
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
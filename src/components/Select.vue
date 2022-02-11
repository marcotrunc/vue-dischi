<template>
  <div>
    <section v-show="labelFlag">
      <label for="research" class="text-white me-2">Cerca per:</label>
      <select name="research" id="research" v-model="elemtentResearch">
        <option value="genere">Genere</option>
        <option value="titolo">Titolo</option>
      </select>
    </section>
    <section :class="{ 'd-none': !elemtentResearch }">
      <Selectedgenre
        @changes="changeSearch"
        :genres="genres"
        v-if="showSelect()"
      />
      <!-- <Selectedtitle @changes-title="changeTitle" :titles="titles" v-else /> -->
    </section>
  </div>
</template>

<script>
import Selectedgenre from "./Selectedgenre.vue";
// import Selectedtitle from "./Selectedtitle.vue";
export default {
  name: "Select",
  props: ["genres", "titles"],
  components: {
    Selectedgenre,
    // Selectedtitle,
  },
  data() {
    return {
      search: "",
      elemtentResearch: "",
      labelFlag: true,
      selectFlag: undefined,
    };
  },
  methods: {
    changeSearch(value) {
      const search = value;
      this.$emit("changes", search);
    },
    showSelect() {
      if (this.elemtentResearch === "genere") {
        this.labelFlag = false;
        return true;
      } else if (
        this.elemtentResearch === "titolo" &&
        this.elemtentResearch !== ""
      ) {
        this.labelFlag = false;
        return false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
</style>
<template>
  <div>
    <h1>{{ animal.name }}</h1>
    <h2>Age: {{ animal.age }} years old</h2>
    <h3>Breed: {{ animal.breed }}</h3>
  </div>
</template>

<script>
import { mapState } from "vuex";

export default {
  data() {
    return {
      animal: {}
    };
  },
  computed: {
    ...mapState(["cats", "dogs"])
  },
  mounted() {
    const animal = this[this.$route.params.species][this.$route.params.id];
    this.animal = animal;
  }
};
</script>

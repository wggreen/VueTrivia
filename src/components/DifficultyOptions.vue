<template>
  <div>
    <button @click="selectDifficulty('easy')">Easy</button>
    <button @click="selectDifficulty('medium')">Medium</button>
    <button @click="selectDifficulty('hard')">Hard</button>
    <button @click="selectDifficulty('all')">All</button>
  </div>
</template>

<script>
export default {
  props: ["difficulty"],
  methods: {
    selectDifficulty(difficulty) {
      this.$emit("difficulty-change", difficulty);
    },
  },
};
</script>

<style>
button {
  margin: 10px;
}
</style>
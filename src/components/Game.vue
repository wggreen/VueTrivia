<template>
  <div>
    <h1>STAR WARS TRIVIA</h1>
    <div class="questions">
      <div v-for="question in trivia" :key="question.id">
        <card :card="question" />
      </div>
    </div>
  </div>
</template>

<script>
import { questions } from "../trivia";
import Card from "./Card";

export default {
  components: { Card },

  data() {
    return {
      trivia: [...questions],
    };
  },
};
</script>

<style>
.questions {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
}
h1 {
  color: yellow;
}
</style>
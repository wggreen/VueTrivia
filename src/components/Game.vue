<template>
  <div>
    <h1>STAR WARS TRIVIA</h1>
    <button @click="hideAnswers" class="flat-button">HIDE ANSWERS</button>
    <button @click="reset" class="flat-button">RESET</button>
    <div class="difficulty-options">
      <difficulty-options
        :difficulty="selectedDifficulty"
        @difficulty-change="handleDifficultyChange"
      />
    </div>
    <div class="questions">
      <div v-for="question in displayedQuestions" :key="question.id">
        <card :card="question" @toggle="toggle" />
      </div>
    </div>
  </div>
</template>

<script>
import { questions } from "../trivia";
import Card from "./Card";
import DifficultyOptions from "./DifficultyOptions.vue";

export default {
  components: { Card, DifficultyOptions },

  data() {
    return {
      questions: [...questions],
      selectedDifficulty: "all",
    };
  },

  methods: {
    toggle(card) {
      card.answerShown = !card.answerShown;
    },
    handleDifficultyChange(difficulty) {
      this.selectedDifficulty = difficulty;
    },
    hideAnswers() {
      this.questions.forEach((t) => (t.answerShown = false));
    },
    reset() {
      this.selectedDifficulty = "all";
      this.questions.forEach((t) => (t.answerShown = false));
    },
  },

  computed: {
    displayedQuestions() {
      if (this.selectedDifficulty === "all") {
        return this.questions;
      }
      return this.questions.filter(
        (t) => t.difficulty === this.selectedDifficulty
      );
    },
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
  margin-top: 0px;
}
.flat-button {
  background: transparent;
  border: none;
  cursor: pointer;
  margin-bottom: 10px;
  font-size: 20px;
  color: goldenrod;
}
</style>
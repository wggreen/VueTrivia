<template>
  <div class="card" :class="{ flipped: card.answerShown }">
    <div class="card-inner">
      <div class="question">
        <h4>{{ card.question }}</h4>
        <div>
          <button>Show Answer</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["card"],
};
</script>

<style>
.card {
  background-color: transparent;
  width: 300px;
  height: 200px;
  border: 1px solid #f1f1f1;
  perspective: 1000px;
  margin-top: 20px;
  background-color: rgb(41, 40, 40);
  color: yellow;
}
</style>
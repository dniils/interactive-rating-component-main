<template>
  <div class="success-result">
    <img
      class="success-result__image"
      src="../assets/images/illustration-thank-you.svg"
      alt="illustration"
    />

    <div class="success-result__selection-result">
      You selected {{ rate }} out of 5
    </div>
    <div class="success-result__title">Thank you!</div>
    <div class="success-result__subtitle">
      We appreciate you taking the time to give a rating. If you ever need more
      support, don’t hesitate to get in touch!
    </div>
  </div>
</template>

<script setup>
import defineProps from "vue";

defineProps({
  rate: Number,
});
</script>

<style lang="scss" scoped>
.success-result {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;

  &__selection-result {
    margin: 0 auto;
    background-color: var(--blue-100);
    padding: 10px 20px;
    border-radius: 40px;
    color: var(--orange);
  }

  &__image {
    margin: 0 auto;
    width: 200px;
  }

  &__title {
    font-size: var(--fs-xl);
    color: var(--white);
    text-align: center;
    font-weight: var(--fw-700);
  }

  &__subtitle {
    font-size: var(--fs-m);
    line-height: 1.5;
    color: var(--grey-200);
    text-align: center;
    font-weight: var(--fw-400);
  }
}
</style>

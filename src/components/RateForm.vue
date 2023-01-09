<template>
  <div class="rate-form">
    <div class="rate-form__image-wrapper">
      <img
        src="../assets/images/icon-star.svg"
        alt="star image"
        class="rate-form__image"
      />
    </div>
    <div class="rate-form__title">How did we do?</div>
    <div class="rate-form__subtitle">
      Please let us know how we did with your support request. All feedback is
      appreciated to help us improve our offering!
    </div>

    <form
      @submit.prevent="emit('submitEvent', rates.selectedRate)"
      class="rate-form__rate-us-form"
    >
      <div class="rate-form__list-wrapper">
        <div
          class="rate-form__radio-button-wrapper"
          v-for="num in rates.rates"
          :key="num"
        >
          <input
            class="rate-form__radio-button-input"
            type="radio"
            :id="num"
            :value="num"
            name="rate"
            v-model="rates.selectedRate"
          />
          <label class="rate-form__radio-button-label" :for="num">
            {{ num }}</label
          >
        </div>
      </div>

      <button class="rate-form__btn-submit">SUBMIT</button>
    </form>
  </div>
</template>

<script setup>
import { ref, defineEmits } from "vue";

const rates = ref({
  rates: [1, 2, 3, 4, 5],
  selectedRate: null,
});

const emit = defineEmits("submitEvent");
</script>

<style lang="scss" scoped>
.rate-form {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;

  &__image-wrapper {
    height: 60px;
    width: 60px;
    background-color: var(--blue-100);
    border-radius: 50%;
    display: flex;
    align-items: center;
  }
  &__image {
    height: 20px;
    margin: 0 auto;
  }

  &__title {
    font-size: var(--fs-xl);
    color: var(--white);
    font-weight: var(--fw-700);
  }

  &__subtitle {
    font-size: var(--fs-m);
    line-height: 1.5;
    color: var(--grey-200);
    font-weight: var(--fw-400);
  }

  &__list-wrapper {
    display: flex;
    justify-content: space-between;
    margin: 40px 0;
  }

  &__radio-button-input {
    margin: 0;
    position: absolute;
    left: -100000px;

    &:checked {
      ~ .rate-form__radio-button-label {
        color: var(--white);
        background-color: var(--orange);
      }
    }
  }

  &__radio-button-wrapper {
    width: 60px;
    height: 60px;
    display: flex;
    align-items: center;
  }

  &__radio-button-label {
    width: 60px;
    height: 60px;
    font-size: var(--fs-m);
    background-color: var(--blue-100);
    border-radius: 50%;
    color: var(--grey-200);
    transition: all 0.2s ease-in-out;
    line-height: 3.5em;
    text-align: center;
    user-select: none;
    font-weight: var(--fw-700);

    &:hover {
      cursor: pointer;

      background-color: var(--grey-100);
      color: var(--white);
    }
  }

  &__btn-submit {
    background-color: var(--orange);
    border: none;
    border-radius: 50px;
    padding: 20px;
    color: var(--white);
    font-size: var(--fs-m);
    font-weight: var(--fw-700);
    width: 100%;
    transition: all 0.2s ease-in-out;

    &:hover {
      background-color: var(--white);
      color: var(--orange);
      cursor: pointer;
    }
  }
}
</style>

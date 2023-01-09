<template>
  <div class="rate-wrapper">
    <div class="rate">
      <rate-form v-if="!submitted" @submit-event="submitEventHandler" />
      <success-result v-else :rate="selectedRate" />
    </div>
  </div>

  <div class="attribution">
    Challenge by
    <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
      >Frontend Mentor</a
    >
    | Coded by
    <a href="https://github.com/dniils" target="blank">Daniil S.</a>
    under
    <a href="https://github.com/i-sukhanov" target="blank">Ivan S.</a>
    mentorship
  </div>
</template>

<script setup>
import { ref } from "vue";
import RateForm from "./components/RateForm.vue";
import SuccessResult from "./components/SuccessResult.vue";

const submitted = ref(false);
const selectedRate = ref(null);

function submitEventHandler(rate) {
  console.log(rate);

  selectedRate.value = rate;
  if (selectedRate.value) submitted.value = true;
  else alert("Please, rate our service from 1 to 5 to submit");
}
</script>

<style lang="scss"></style>

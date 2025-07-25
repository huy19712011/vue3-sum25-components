<script setup>
import { onMounted, onUnmounted, ref } from "vue";
import CoffeePlan from "./CoffeePlan.vue";

// defineProps({
//   plans: Array,
// });

const plans = ref(["The Single", "The Curious", "The Addict", "The Hacker"]);

const selectedCoffeePlan = ref();

const plansWrapper = ref();

function handleSelectCoffeePlan(name) {
  selectedCoffeePlan.value = name;
}

onMounted(() => {
  // console.log(document.querySelector(".plans"));
  console.log(plansWrapper.value);
});

onUnmounted(() => {
  console.log("By by plan picker!!!");
  clearInterval(interval);
});

const count = ref(0);
const interval = setInterval(() => {
  count.value++;
  console.log("hello");
}, 1000);
</script>
<template>
  <div ref="plansWrapper" class="plans">
    {{ selectedCoffeePlan }}
    {{ count }}
    <CoffeePlan
      v-for="plan in plans"
      :key="plan"
      :name="plan"
      :selected="plan === selectedCoffeePlan"
      @selected="handleSelectCoffeePlan"
    >
    </CoffeePlan>
  </div>
</template>

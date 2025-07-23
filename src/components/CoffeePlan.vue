<script setup>
import { ref } from "vue";

// defineProps(["name"]);
const props = defineProps({
  name: { type: String, default: "Default Plan" },
  //   price: { type: Number, required: false },
  selected: { type: Boolean, default: false },
});

// const selected = ref(false);

const emit = defineEmits(["selected"]);

const selectPlan = () => {
  // selected.value = !selected.value;
  emit("selected", props.name);
};
</script>

<template>
  <div class="plan" :class="{ 'active-plan': selected }" @click="selectPlan">
    <div class="description">
      <span class="title"> {{ name }} </span>
    </div>
  </div>
</template>

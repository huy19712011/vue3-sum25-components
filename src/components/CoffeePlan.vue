<script setup>
import { ref } from "vue";

// defineProps(["name"]);
const props = defineProps({
  name: {
    type: String,
    default: "Default Plan",
    validator(value) {
      return value.startsWith("The");
    },
  },
  //   price: { type: Number, required: false },
  selected: { type: Boolean, default: false },
});

// const selected = ref(false);

const emit = defineEmits({
  hiThere: null, // do not check validate for event named 'hiThere'
  selected(payload) {
    return typeof payload === "string";
  },
});

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

<script setup>
// defineProps(["name"]);
defineProps({
  name: { type: String, default: "Default Plan" },
  //   price: { type: Number, required: false },
});
</script>

<template>
  <div class="plan">
    <div class="description">
      <span class="title"> {{ name }} </span>
    </div>
  </div>
</template>

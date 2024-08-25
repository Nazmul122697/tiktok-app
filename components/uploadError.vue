<template lang="">
  <div class="w-[100%] relative flex justify-center">
    <div
      class="absolute z-50 py-3 mx-auto text-white bg-black rounded-sm top-6 bg-opacity-70 px-14"
      :class="errorType ? 'visible' : 'invisible'"
    >
      {{ error }}
    </div>
  </div>
</template>
<script setup>
const props = defineProps(["errorType"]);
const { errorType } = toRefs(props);

let error = ref("");

watch(
  () => errorType.value,
  () => {
    if (errorType.value == "caption") {
      error.value = "Maximum 150 characters.";
    } else if (errorType.value == "bio") {
      error.value = "Maximum 80 characters.";
    } else if (errorType.value == "file") {
      error.value = "Unsupported file. Use MP4 instend.";
    } else {
      error.value = "";
    }
  }
);
</script>

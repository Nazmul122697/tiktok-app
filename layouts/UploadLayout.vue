<template lang="">
  <div class="bg-[#F8F8F8] h-[100vh]">
    <topNav />
    <div class="flex justify-between mx-auto w-full px-2 max-w-[1140px]  ">
      <slot />
    </div>
  </div>
</template>
<script setup>
import topNav from "../components/topNav.vue";
import SideNavMain from "~/components/SideNavMain.vue";
const route = useRoute();
</script>

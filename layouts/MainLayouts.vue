<template lang="">
  <topNav />
  <div 
  :class="route.fullPath === '/'? 'max-w-[1140px]':''"
  class="flex justify-between mx-auto w-full lg:px-2.5 px-0">
    <div>
      <SideNavMain />
    </div>
    <slot />
  </div>
</template>
<script setup>
import topNav from "../components/topNav.vue";
import SideNavMain from "~/components/SideNavMain.vue";
const route = useRoute()
</script>

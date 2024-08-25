<template lang="">
  <div
    id="SideNavMain"
    class="fixed z-20 bg-white pt-[70px] h-full lg:border-r-o border-r w-[75px] overflow-auto"
    :class="route.fullPath === '/' ? 'lg:w-[310px]' : 'lg:w-[220px]'"
  >
    <div class="lg:w-full w-[55px] mx-auto">
      <nuxt-link to="/">
        <MenuItem
          colorString="#F02C56"
          sizeString="30"
          iconString="For You"
        ></MenuItem>
      </nuxt-link>
      <MenuItem
        colorString="#F02C56"
        sizeString="27"
        iconString="Following"
      ></MenuItem>
      <MenuItem
        colorString="#000000"
        sizeString="27"
        iconString="Live"
      ></MenuItem>
      <div class="border-b lg:ml-2 mt-2"></div>

      <div
        class="lg:block hidden text-xs text-gray-600 font-semibold pt-4 pb-2 px-2"
      >
        Suggested Acoounts
      </div>
      <div class="lg:hidden block pt-3" />
      <div class="cursor-pointer">
        <MenuItemFollow />
      </div>
      <button class="lg:block hidden text-[#F02c56] pt-1.5 pl-2 text-[13px]">
        See All
      </button>
      <div class="border-b lg:ml-2 mt-2"></div>
      <div
        class="lg:block hidden text-xs text-gray-600 font-semibold pt-4 pb-2 px-2"
      >
        Following Acoounts
      </div>
      <div class="lg:hidden block pt-3" />
      <div class="cursor-pointer">
        <MenuItemFollow />
      </div>
      <button class="lg:block hidden text-[#F02c56] pt-1.5 pl-2 text-[13px]">
        See More
      </button>

      <div class="lg:block hidden border-b lg:ml-2 mt-2" />
      <div class="lg:block hidden text-[11px] text-gray-500">
        <div class="pt-4 px-2">Help Safety Terms Privacy</div>
        <div class="pt-4 px-2">Privacy Center</div>
        <div class="pt-4 px-2">Creator Academy</div>
        <div class="pt-4 px-2">Community Guidelines</div>
        <div class="pt-4 px-2">© 2024 TikTok</div>
      </div>
      <div class="pb-14"></div>
    </div>
  </div>
</template>
<script setup>
const route = useRoute();
</script>

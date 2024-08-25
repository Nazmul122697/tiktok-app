<template lang="">
  <div id="topNav" class="fixed bg-white z-30 flex w-full border-b h-[61px]">
    <div
      :class="route.fullPath === '/' ? 'max-w-[1150px]' : ''"
      class="flex items-center justify-between w-full px-6 mx-auto"
    >
      <div :class="route.fullPath === '/' ? 'w-[80%]' : 'lg:w-[20%] w-[70%]'">
        <nuxt-link to="/">
          <img width="115" src="~/assets/images/tiktok-logo.png" />
        </nuxt-link>
      </div>
      <div
        class="hidden md:flex items-center bg-[#f1f1f1] p-1 rounded-full max-w-[380px] w-full"
      >
        <input
          type="text"
          class="w-full pl-3 bg-transparent placeholder-[#838383] text-[15px] focus:outline-none"
          placeholder="Search Accounts"
        />

        <div class="px-3 py-1 flex items-center border-l border-l-gray-300">
          <Icon name="ic:outline-search" size="22" color="#A1A2A7" />
        </div>
      </div>

      <div
        class="flex items-center justify-end gap-3 min-w-[275px] max-w-[320px] w-full"
      >
        <button
          class="flex items-center border rounded-sm px-3 py-[6px] hover:bg-gray-100"
        >
          <Icon name="mdi:plus" size="22" color="#000" />
          <span class="px-2 font-medium text-[15px]">Upload</span>
        </button>

        <div v-if="false" class="flex items-center">
          <button
            class="flex items-center bg-[#F02c56] text-white border rounded-md px-3 py-[6px]"
          >
            <span class="mx-4 font-medium text-[15px]"> Log In</span>
          </button>

          <Icon name="mdi:dots-vertical" size="25" color="#161724" />
        </div>

        <div class="flex items-center">
          <Icon
            class="ml-1 mr-4"
            name="ri:send-plane-fill"
            size="30"
            color="#161724"
          />
          <Icon
            class="mr-5"
            name="mdi:message-text-outline"
            size="27"
            color="#161724"
          />
          <div class="relative">
            <button class="mt-1" @click="$e => showMenu = !showMenu">
              <img
                class="rounded-full" 
                src="https://picsum.photos/id/83/300/320"
                width="33"
              />
            </button>

            <div
              id="PopUpMenu" v-if="showMenu"
              class="absolute bg-white rounded-lg py-1.5 w-[200px] shadow-xl top-[43px] -right-2"
            > 
              <NuxtLink @click="$event => showMenu = false"
                class="flex items-center justify-start py-3 px-2 hover:bg-gray-100 cursor-pointer"
              >
                <Icon name="ph:user" size="20" />
                <span class="pl-2 pt-2 font-semibold text-sm" >Profile</span>
              </NuxtLink>

              <div @click="$event => showMenu = false"
                class="flex items-center justify-start py-3 px-1.5 hover:bg-gray-100 cursor-pointer"
              >
                <Icon name="material-symbols:logout-rounded" size="20" />
                <span class="pl-2 pt-2 font-semibold text-sm" >Log Out</span>
              </div>


            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
const route = useRoute();
let showMenu = ref(false);
</script>

<template lang="">
  <div id="PostMain" class="flex py-6 border-b">
    <div class="cursor-pointer">
      <img
        class="rounded-full max-h-[60px]"
        width="60"
        src="https://picsum.photos/id/8/300/320"
      />
    </div>
    <div class="w-full px-4 pl-3">
      <div class="flex items-center justify-between pb-0.5">
        <button>
          <span class="font-bold cursor-pointer hover:underline"
            >User Name</span
          >
          <span class="text-[13px] text-light text-gray-500 pl-1 cursor-pointer"
            >User Name</span
          >
        </button>
        <button
          class="border text-[15px] px-[21px] py-0.5 text-[#F02c56] border-[#F02c56] hover:bg-[#ffeef2] font-semibold rounded-md"
        >
          Follow
        </button>
      </div>
      <div
        class="text-[15px] pb-0.5 break-words md:max-w-[400px] max-w-[300px]"
      >
        This is some text
      </div>
      <div class="text-[14px] text-gray-500 pb-0.5">
        #fun #cool #superAwsome
      </div>
      <div class="text-[14px] pb-0.5 flex items-center font-semibold">
        <Icon name="mdi:music" size="17" />
        <div class="px-1">Original Music</div>
        <Icon name="mdi:heart" size="20" />
      </div>

      <div class="mt-2.5 flex">
        <div
          class="relative min-h-[480px] max-h-[580px] max-w-[200px] flex items-center bg-black rounded-xl cursor-pointer"
        >
          <video
            src="~/assets/videos/223928_small.mp4"
            ref="video"
            loop
            muted
            class="object-cover h-full mx-auto rounded-xl"
          />
          <img
            class="absolute right-2 bottom-14"
            width="90"
            src="/assets/images/tiktok-logo-white.png"
          />
        </div>
        <div class="relative mr-[75px]">
          <div class="absolute bottom-0 pl-2">
            <div class="pb-4 text-center">
              <button class="p-2 bg-gray-200 rounded-full cursor-pointer">
                <Icon name="mdi:heart" size="25" />
              </button>
              <span class="text-xs text-gray-800">55</span>
            </div>
            <div class="pb-4 text-center">
              <button class="p-2 bg-gray-200 rounded-full cursor-pointer">
                <Icon name="bx:bxs-message-rounded-dots" size="25" />
              </button>
              <span class="text-xs text-gray-800">55</span>
            </div>
            <div class="pb-4 text-center">
              <button class="p-2 bg-gray-200 rounded-full cursor-pointer">
                <Icon name="ri:share-forward-fill" size="25" />
              </button>
              <span class="text-xs text-gray-800">55</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
const video = ref(null);
onMounted(() => video.value.play());
</script>

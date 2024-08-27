<template>
  <div
    class="relative brightness-90 hover:brightness-[1.1] cursor-pointer"
    @mouseenter="($event) => isHover(true)"
    @mouseleave="($event) => isHover(false)"
  >
    <div
      v-if="!isLoaded"
      class="absolute flex items-center justify-center top-0 left-0 aspect-[3/4] w-full object-cover rounded-md bg-black"
    >
      <Icon
        name="mingcute:loading-line"
        size="100"
        class="ml-1 animate-spin"
        style="color: aliceblue"
      />
    </div>

    <div>
      <video
        class="aspect-[3/4] object-cover rounded-md"
        ref="video"
        muted
        loop
        src="~/assets/videos/223928_small.mp4"
      />
    </div>

    <div class="px-1">
      <div class="text-gray-700 text-[15px] pt-1 font-bold text-xs">
        This is Some Text
      </div>
      <div class="flex items-center -ml-1 text-xs font-bold text-gray-600">
        <Icon name="gg:loadbar-sound" size="20" />3%
        <Icon name="tabler:alert-circle" class="ml-1" size="16" />
      </div>
    </div>
  </div>
</template>
<script setup>
defineProps(["post"]);

const route = ref(null);
const router = ref(false);

let video = ref(null);
let isLoaded = ref(false);

onMounted(() => {
  if (video.value) {
    video.value.addEventListener("loadeddata", (e) => {
      if (e.target) {
        setTimeout(() => {
          isLoaded.value = true;
        }, 200);
      }
    });
  }
});

onBeforeUnmount(() => {
  video.value.pause();
  video.value.currentTime = 0;
  video.value.src = "";
});

const isHover = (bool) => {
  if (bool) {
    video.value.play();
  } else {
    video.value.pause();
  }
}; 
</script>

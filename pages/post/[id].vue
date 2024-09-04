<template lang="">
  <div
    id="PostPage"
    class="fixed top-0 left-0 z-50 justify-between w-full h-full overflow-auto bg-black lg:flex lg-black lg:overflow-hidden"
  >
    <div class="lg:w-[calc(100%-540px)] h-full relative">
      <nuxt-link
        to=""
        class="absolute z-20 m-5 bg-gray-700 rounded-full p-1.5 hover:bg-gray-800"
      >
        <Icon name="mingcute:close-fill" style="color: white" size="27" />
      </nuxt-link>

      <div v-if="true">
        <button
          :disabled="!isLoaded"
          @click="($event) => loopThroughPostsUp()"
          class="absolute z-20 flex items-center justify-center bg-gray-700 rounded-full right-4 top-4 p-1.5 hover:bg-gray-800"
        >
          <Icon name="mdi:chevron-up" size="30" style="color: #fff" />
        </button>

        <button
          :disabled="!isLoaded"
          @click="($event) => loopThroughPostsDown()"
          class="absolute z-20 flex items-center justify-center bg-gray-700 rounded-full right-4 top-20 p-1.5 hover:bg-gray-800"
        >
          <Icon name="mdi:chevron-down" size="30" style="color: #fff" />
        </button>
      </div>

      <img
        class="absolute top-[18px] left-[70px] rounded-full lg:mx-0 mx-auto"
        width="45"
        src="~/assets/images/tiktok-logo-small.png"
      />
      <video
        class="absolute object-cover w-full my-auto z-[-1] h-screen"
        src="~/assets/videos/223928_small.mp4"
      />

      <div
        v-if="!isLoaded"
        class="flex items-center justify-center h-screen bg-black bg-opacity-70 lg:min-[480px]"
      >
        <Icon
          class="ml-0 animate-spin"
          name="mingcute:loading-line"
          size="100"
          style="color: #fff"
        />
      </div>

      <div class="bg-black bg-opacity-70 lg:min-w-[480px]">
        <video
          class="h-screen mx-auto"
          src="~/assets/videos/223928_small.mp4"
          v-if="true"
          loop
          muted
          ref="video"
        />
      </div>
    </div>
    <div
      id="InfoScreen"
      v-if="true"
      class="lg:max-w-[550px] relative w-full h-full bg-white"
    >
      <div class="py-7" />
      <div class="flex items-center justify-between px-8">
        <div class="flex items-center">
          <nuxt-link to="">
            <img
              class="mx-auto rounded-full lg:mx-0"
              width="40"
              src="https://picsum.photos/id/8/300/320"
            />
          </nuxt-link>

          <div class="pt-0.5 ml-3">
            <div class="text-[17px] font-semibold">User Name</div>
            <div class="text-[13px] font-light -mt-5">
              User Name
              <span class="relative -top-[2px] text-[30px] pr-0.5">.</span>
              <span class="font-medium">Date Here</span>
            </div>
          </div>
        </div>
        <Icon
          name="material-symbols:delete-outline-sharp"
          size="25"
          @click="($event) => deletePost()"
          v-if="true"
          class="cursor-pointer"
        />
      </div>
      <div class="px-8 mt-4 text-sm">This is the Post Here</div>
      <div class="px-8 mt-4 text-sm font-bold">
        <Icon name="mdi:music" size="17" />
        Original sound - User Name
      </div>

      <div class="flex items-center px-8 mt-8">
        <div class="flex items-center pb-4 text-center">
          <button class="p-2 bg-gray-200 rounded-full cursor-pointer">
            <Icon name="mingcute:heart-fill" size="25" />
          </button>
        </div>
        <div class="pl-2 pr-4 text-xs font-semibold text-gray-800">123</div>
        <div class="flex items-center pb-4 text-center">
          <div class="p-2 bg-gray-200 rounded-full cursor-pointer">
            <Icon name="mingcute:message-3-fill" size="25" />
          </div>
        </div>
        <div class="pl-2 pr-4 text-xs font-semibold text-gray-800">123</div>
      </div>

      <div
        id="comments"
        class="bg-[#F8f8f8] z-0 h-[calc(100%-273px)] border-t-2 overflow-auto"
      >
        <div class="pt-2" />
        <div v-if="false" class="mt-6 text-xl text-center text-gray-500">
          No comments
        </div>

        <div v-else class="relative flex justify-between px-8 mt-4">
          <div class="relative flex items-center w-full">
            <nuxt-link to="">
              <img
                class="absolute top-0 mx-auto rounded-full lg:mx-0"
                width="40"
                src="https://picsum.photos/id/8/300/320"
              />
            </nuxt-link>
            <div class="ml-14 pt-0.5 w-full">
              <div
                class="text-[18px] font-semibold flex items-center justify-between"
              >
                User Name
                <Icon
                  v-if="true"
                  @click="($event) => deleteComment()"
                  class="cursor-pointer"
                  name="material-symbols:delete-outline-sharp"
                  size="25"
                />
              </div>

              <div class="text-[15px] font-light">
                Ea et aliqua cillum in reprehenderit occaecat occaecat irure
                occaecat. Deserunt sit velit ipsum dolor qui amet commodo veniam
                proident et eiusmod. Consectetur aute eiusmod labore veniam.
                Cupidatat eu dolore velit qui occaecat irure id laboris sunt sit
                in sit exercitation culpa. Id reprehenderit minim reprehenderit
                in est duis et ad occaecat et occaecat.
              </div>
            </div>
          </div>
        </div>
        <div class="mb-28" />
      </div>

      <div
        id="CreateComment"
        v-if="true"
        class="absolute bottom-0 flex items-center justify-between lg:max-w-[550px] bg-white h-[85px] w-full py-5 px-8 border-t-2"
      >
        <div
          :class="
            inputFocused
              ? 'border-2 border-gray-400'
              : 'border-2 border-[#F1f1f2]'
          "
          class="bg-[#f1f1f2] flex items-center rounded-lg w-full lg:max-w-[420px]"
        >
          <input
            v-model="comment"
            @focus="($event) => (inputFocused = true)"
            @blur="($event) => (inputFocused = false)"
            class="bg-[#f1f1f2] text-[14px] focus:ouline-none w-full lg:max-w-[420px] p-2 rounded-lg"
            type="text"
            placeholder="Add Comment ......."
          />
        </div>
        <button>Post</button>
      </div>
    </div>
  </div>
</template>
<script setup>
let inputFocused = ref(false);
let comment = ref(null);

let route = ref(null);
let router = ref();

let video = ref(null);
let isLoaded = ref(false);

onMounted(() => {
  video.value.play()
  isLoaded.value = true
  // video.value.addEventListener("loadeddata", (e) => {
  //   if (e.target) {
  //     setTimeout(() => {
  //       isLoaded.value = true;
  //     }, 50);
  //   }
  // });
});

onBeforeUnmount(() => {
  video.value.pause();
  video.value.currentTime = 0;
  video.value.src = "";
});

watch(
  () => isLoaded.value,
  () => {
    if (isLoaded.value) {
      setTimeout(() => video.value.play(), 500);
    }
  }
);
</script>

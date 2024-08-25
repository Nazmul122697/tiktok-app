<template>
  <UploadLayout>
    <div
      class="w-full ml-[80px] mb-[40px] bg-white shadow-lg rounded-md py-6 md:px-10 px-4 mt-[70px]"
    >
      <div>
        <div class="text-[23px] font-semibold">Upload Video</div>
        <div class="text-gray-400 mt-1">Post a video to your account</div>
      </div>
      <div class="mt-8 md:flex gap-6">
        <label
          v-if="false"
          for="fileInput"
          class="md:mx-0 mx-auto mt-4 mb-6 flex flex-col items-center justify-center w-full max-w-[260px] h-[478px] text-center p-3 border-2 border-dashed border-gray-300 rounded-lg hover:bg-gray-100 cursor-pointer"
        >
          <Icon name="solar:cloud-upload-linear" size="40px" color="#b3b3b1" />
          <div class="mt-4 text-[17px]">Select video to upload</div>
          <div class="mt-1.5 text-gray-500 text-[13px]">
            Or drag and drop a file
          </div>
          <div class="mt-12 text-gray-400 text-sm">MP4</div>
          <div class="mt-2 text-gray-400 text-[13px]">Up to 30 minutes</div>
          <div class="mt-2 text-gray-400 text-[13px]">Less then 2 GB</div>
          <div
            class="px-2 py-1.5 text-white text-[15px] w-[80%] bg-[#f02c56] mt-8 rounded-sm"
          >
            Select file
          </div>
          <input type="file" ref="file" id="fileInput" accept=".mp4" hidden />
        </label>
        <div
          v-else
          class="md:mx-0 mx-auto mt-4 md:mb-12 mb-16 flex items-center justify-center w-full max-w-[260px] h-[540px] p-3 cursor-pointer relative rounded-2xl"
        >
          <div class="bg-black h-full w-full" />
          <img
            class="absolute z-20 pointer-events-note"
            src="~/assets/images/mobile-case.png"
          />
          <img
            class="absolute right-4 button-5 z-20"
            width="90"
            src="~/assets/images/tiktok-logo-white.png"
          />
          <video
            autoplay
            loop
            muted
            class="absolute rounded-xl object-cover z-10 p-[13px] w-full h-full"
            src="/public/223928_small.mp4"
          />
          <div
            class="absolute -bottom-12 flex items-center shadow justify-between z-58 rounded-xl border w-full p-2 border-gray-300"
          >
            <div class="flex items-center truncate">
              <Icon
                name="clarity:success-standard-line"
                size="16"
                class="min-w-[16px]"
              />
              <div class="text-[11px] pl-1 truncate text-ellipsis">
                Video Name
              </div>
            </div>
            <button class="text-[11px] ml-2 font-semibold">Change</button>
          </div>
        </div>

        <div class="mt-4 mb-6">
          <div class="flex bg-[#f8f8f8] py-4 px-6">
            <div>
              <Icon class="mr-4" size="20" name="mdi:box-cutter-off" />
            </div>

            <div>
              <div class="text-semibold text-[15px] mb-1.5">
                Divide videos and edit
              </div>
              <div class="text-semibold text-[13px] text-gray-400">
                You can quickly divide videos into multiple parts, remove
                redundant parts and turn lanscape videos into portrait videos
              </div>
            </div>
            <div
              class="flex justify-end max-w-[130px] w-full h-full text-center my-auto"
            >
              <button
                class="px-8 py-1.5 text-white text-[15px] bg-[#F02c56] rounded-sm"
              >
                Edit
              </button>
            </div>
          </div>

          <div class="mt-5">
            <div class="flex justify-between items-center">
              <div>Caption</div>
              <div>0/150</div>
            </div>
            <input maxlength="150" type="text" class="w-full border p-2.5 rounded-md focus:outline-none"/>
            
          </div>
        </div>
      </div>
    </div>
  </UploadLayout>
</template>
<script setup>
import UploadLayout from "~/layouts/UploadLayout.vue";
</script>

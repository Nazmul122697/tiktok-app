<template>
  <uploadError :errorType="errorType" />
  <UploadLayout>
    <div
      class="w-full ml-[80px] mb-[40px] bg-white shadow-lg rounded-md py-6 md:px-10 px-4 mt-[70px]"
    >
      <div>
        <div class="text-[23px] font-semibold">Upload Video</div>
        <div class="mt-1 text-gray-400">Post a video to your account</div>
      </div>
      <div class="gap-6 mt-8 md:flex">
        <label
          v-if="!fileDisplay"
          @drop.prevent="onDrop"
          @dragover.prevent=""
          for="fileInput"
          class="md:mx-0 mx-auto mt-4 mb-6 flex flex-col items-center justify-center w-full max-w-[260px] h-[478px] text-center p-3 border-2 border-dashed border-gray-300 rounded-lg hover:bg-gray-100 cursor-pointer"
        >
          <Icon name="solar:cloud-upload-linear" size="40px" color="#b3b3b1" />
          <div class="mt-4 text-[17px]">Select video to upload</div>
          <div class="mt-1.5 text-gray-500 text-[13px]">
            Or drag and drop a file
          </div>
          <div class="mt-12 text-sm text-gray-400">MP4</div>
          <div class="mt-2 text-gray-400 text-[13px]">Up to 30 minutes</div>
          <div class="mt-2 text-gray-400 text-[13px]">Less then 2 GB</div>
          <div
            class="px-2 py-1.5 text-white text-[15px] w-[80%] bg-[#f02c56] mt-8 rounded-sm"
          >
            Select file
          </div>
          <input
            type="file"
            @input="onChange"
            ref="file"
            id="fileInput"
            accept=".mp4"
            hidden
          />
        </label>
        <div
          v-else
          class="md:mx-0 mx-auto mt-4 md:mb-12 mb-16 flex items-center justify-center w-full max-w-[260px] h-[540px] p-3 cursor-pointer relative rounded-2xl"
        >
          <div class="w-full h-full bg-black" />
          <img
            class="absolute z-20 pointer-events-note"
            src="~/assets/images/mobile-case.png"
          />
          <img
            class="absolute z-20 right-4 button-5"
            width="90"
            src="~/assets/images/tiktok-logo-white.png"
          />
          <video
            autoplay
            loop
            muted
            class="absolute rounded-xl object-cover z-10 p-[13px] w-full h-full"
            :src="fileDisplay"
          />
          <div
            class="absolute flex items-center justify-between w-full p-2 border border-gray-300 shadow -bottom-12 z-58 rounded-xl"
          >
            <div class="flex items-center truncate">
              <Icon
                name="clarity:success-standard-line"
                size="16"
                class="min-w-[16px]"
              />
              <div class="text-[11px] pl-1 truncate text-ellipsis">
                {{fileData.name}}
              </div>
            </div>
            <button @click="$event=>clearVideo()" class="text-[11px] ml-2 font-semibold">Change</button>
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
            <div class="flex items-center justify-between">
              <div>Caption</div>
              <div>{{caption.length}}/150</div>
            </div>
            <input
              v-model="caption"
              maxlength="150"
              type="text"
              class="w-full border p-2.5 rounded-md focus:outline-none"
            />
          </div>
          <div class="flex gap-3">
            <button
              @click="($event) => discardVideo()"
              class="px-10 py-2.5 mt-8 border text-[16px] hover:bg-gray-100 rounded-sm"
            >
              Discard
            </button>
            <button
              class="px-10 py-2.5 mt-8 border text-[16px] bg-[#F02c56] text-white rounded-sm"
            >
              Post
            </button>
          </div>
        </div>
      </div>
    </div>
  </UploadLayout>
</template>
<script setup>
import UploadLayout from "~/layouts/UploadLayout.vue";

let file = ref(null);
let fileDisplay = ref(null);
let errorType = ref(null);
let caption = ref("");
let fileData = ref(null);
let errors = ref(null);
let isUploading = ref(false);

watch(() => caption.value,(caption) =>{
  if(caption.length >= 150){
    errorType.value = 'caption'
    return
  }
  errorType.value = null
})

let onChange = () => {
  fileDisplay.value = URL.createObjectURL(file.value.files[0]);
  fileData.value = file.value.files[0];
};

const onDrop = (e) => {
  errorType.value = "";
  file.value = e.dataTransfer.files[0];
  fileData.value = e.dataTransfer.files[0];

  let extension = file.value.name.substring(
    file.value.name.lastIndexOf(".") + 1
  );

  if (extension !== "mp4") {
    errorType.value = "file";
    return;
  }

  fileDisplay.value = URL.createObjectURL(e.dataTransfer.files[0]);
};

const discardVideo = () => {
  file.value = null;
  fileData.value = null;
  fileDisplay.value = null;
  caption.value = "";
};

const clearVideo = () => {
  file.value = null;
  fileData.value = null;
  fileDisplay.value = null;
};
</script>

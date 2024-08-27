<template lang="">
  <MainLayouts>
    <div
      class="pt-[90px] 2xl:pl-[185px] lg:pl-[160px] lg:pr-0 pr-2 w-[calc(100%-90px)] max-w-[1800px] 2xl:mx-auto"
    >
      <div class="flex w-[calc(100vw-230px)]">
        <img
          class="max-w-[120px] rounded-full"
          src="https://picsum.photos/id/8/300/320"
        />

        <div class="w-full ml-5">
          <div class="text-[30px] font-bold truncate">User Name</div>
          <div class="text-[18px] truncate">User Name</div>
          <button
            v-if="true"
            class="flex rounded-md item-center py-1.5 px-3.5 mt-3 text-[15px] font-semibold border hover:bg-gray-100"
          >
            <Icon name="mdi:pencil" size="18" class="mt-0.5 mr-1" />
            <div>Edit Profile</div>
          </button>
          <button
            v-else
            class="flex items-center rounded-md py-1.5 px-8 mt-3 text-[15px] font-semibold border bg-[#f02c56] text-white"
          >
            Follow
          </button>
        </div>
      </div>
      <div class="flex items-center pt-4">
        <div class="mr-4">
          <span class="font-bold">10K</span>
          <span class="font-light text-gray-500 text-[15px] pl-1.5"
            >Following</span
          >
        </div>
        <div class="mr-4">
          <span class="font-bold">40K</span>
          <span class="font-light text-gray-500 text-[15px] pl-1.5"
            >Followers</span
          >
        </div>
        <div class="mr-4">
          <span class="font-bold">44K</span>
          <span class="font-light text-gray-500 text-[15px] pl-1.5">Likes</span>
        </div>
      </div>
      <div
        class="pt-4 mr-4 font-light text-gray-500 text-[15px] pl-1.5 max-w-[500px]"
      >
        This is Bio Section
      </div>
      <div class="flex items-center w-full pt-4 border-b">
        <div
          class="py-2 text-center w-60 text-[17px] font-semibold border-b-2 border-b-black"
        >
          Videos
        </div>
        <div
          class="py-2 text-center text-gray-500 w-60 text-[17px] font-semibold"
        >
          <Icon name="material-symbols:lock-open" class="" />Liked
        </div>
      </div>

      <div
        class="grid grid-cols-2 gap-2 mt-4 2xl:grid-cols-6 xl:grid-cols-5 lg:grid-cols-4 md:grid-cols-3"
      >
        <PostUser />
        <PostUser />
      </div>
    </div>
  </MainLayouts>
</template>
<script setup>
import MainLayouts from "~/layouts/MainLayouts.vue";
import PostUser from "~/components/PostUser.vue";
</script>

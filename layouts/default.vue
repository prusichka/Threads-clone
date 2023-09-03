<script setup lang="ts">
const route = useRoute();
const activeRoute = computed(() => {
  console.log(route);
});
</script>

<template>
  <div id="defaultLayout" class="bg-black fixed w-[calc(100%+1px)] h-full">
    <div class="w-full max-w-[500px] mx-auto">
      <div
        id="topMenu"
        class="w-full flex items-center justify-center px-2 h-10 my-2"
      >
        <img
          class="w-[35px]"
          src="/threads-logo.png"
          alt="logo"
          width="35"
          height="35"
        />
        {{ activeRoute }}
      </div>
    </div>

    <div class="flex w-full max-w-[500px] mx-auto h-screen">
      <slot></slot>
    </div>

    <div
      id="bottomNav"
      class="fixed z-50 bottom-0 flex w-full h-[70px] border-t border-r-gray-700 bg-black"
    >
      <div
        class="flex w-full max-w-[500px] mx-auto items-center justify-around"
      >
        <button @click="navigateTo('/')" class="w-full h-full">
          <Icon name="material-symbols:home-outline" size="35" color="#fff" />
        </button>
        <button @click="navigateTo('/')" class="w-full h-full">
          <Icon
            name="material-symbols:edit-square-outline-rounded"
            class="mb-1"
            size="32"
            color="#fff"
          />
        </button>
        <button @click="navigateTo('/')" class="w-full h-full">
          <Icon name="ph:sign-out" size="32" color="#fff" />
        </button>
      </div>
    </div>
  </div>
</template>

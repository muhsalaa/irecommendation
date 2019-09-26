<template>
  <div class="flex">
    <div class="flex top-0 w-full h-16 items-center px-4 fixed bg-green-400">
        <i
          class="text-white text-center text-3xl cursor-pointer block"
          @click="toggleSideBar"
          :class="[active ? 'fa fa-times' : 'fa fa-bars']"
        ></i>
    </div>
    <div class="bg-white h-screen overflow-y-auto w-64 inline-block" :class="[active ? '' : 'hidden']">
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
      <p>asdasdasd</p>
    </div>
    <div
      class="inline-block w-full h-screen overflow-y-auto"
      :class="{'w-full': !active}"
    >
      <div class="sm:px-16">
        <div class="h-screen w-full bg-red-200"></div>
        <div class="h-screen w-full bg-red-200"></div>
      </div>
    </div>
  </div>
</template>

<script>
import sideBar from "./components/Sidebar";

export default {
  data() {
    return {
      active: true
    };
  },
  methods: {
    toggleSideBar() {
      this.active = !this.active;
    }
  },
  components: {
    sideBar
  }
};
</script>

<style>
</style>

<template>
   <div class="flex top-0 w-full h-16 items-center justify-between px-4 z-20 fixed bg-black">
    <div class="flex items-center">
      <i
        class="text-white text-center text-3xl cursor-pointer inline mr-2"
        @click="toggleSideBar"
        :class="[active ? 'fa fa-times' : 'fa fa-bars']"
      ></i>
      <h2 class="text-white text-lg sm:text-xl font-black font-sans inline">iRecommend</h2>
    </div>
    <div class="flex items-center" :class="{'hidden': !user}">
      <label class="text-white text-md mr-2 hidden sm:block" for="toggle">{{ toggle ? 'Past Profile' : 'Recommended Course' }}</label>
      <toggle-button
        id="toggle"
        :color="{checked: '#ffffff', unchecked: '#808080', disabled: '#CCCCCC'}"
        :switch-color="{checked: '#000', unchecked: '#fff'}"
        @change="togglePage"
      ></toggle-button>
    </div>
  </div>
</template>

<script>
import { ToggleButton } from 'vue-js-toggle-button';

export default {
  props: ['toggleSideBar', 'toggle', 'user', 'togglePage', 'active'],
  components: {
    ToggleButton,
  }
}
</script>

<style>

</style>
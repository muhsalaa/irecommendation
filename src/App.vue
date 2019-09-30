<template>
  <div class="sm:flex pt-16">
    <nav-bar 
      :active="active" 
      :toggleSideBar="toggleSideBar" 
      :toggle="toggle" 
      :user="user"
      :togglePage="togglePage"></nav-bar>
    <side-bar 
      :active="active" 
      @setUser="setUser" 
      :user="user"></side-bar>

    <div
      class="sm:w-full flex flex-col sm:justify-center sm:items-center sm:p-32"
      :class="{'hidden': user}"
    >
      <h1 class="font-black text-xl mb-1">Please choose a user to display</h1>
      <a @click="toggleSideBar" class="p-1 bg-blue-700 text-white rounded font-black cursor-pointer hover:bg-blue-500">Choose User</a>
    </div>
    
    <div
      class="h-screen w-full"
      :class="{'hidden': !user || toggle}"
    >
      <div class="pt-2 sm:pt-8">
        <h2 class="pl-5 sm:pl-10 md:pl-20 font-black text-md sm:text-lg">Course Recommendation</h2>
        <swiper :options="swiperOption" class="p-2 sm:p-4 md:p-5 mb-2 pl-5 sm:pl-10 md:pl-20">
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/271/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/272/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/273/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/274/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/275/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/276/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/277/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/278/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/279/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/270/400/300" alt="Sunset in the mountains"></swiper-slide>
        </swiper>
      </div>
    </div>

    <div
      class="h-screen w-full"
      :class="{'hidden': !user || !toggle}"
    >
      <div class="pt-2 sm:pt-8">
        <h2 class="pl-5 sm:pl-10 md:pl-20 font-black text-md sm:text-lg">Past Profile</h2>
        <swiper :options="swiperOption" class="p-2 sm:p-4 md:p-5 mb-2 pl-5 sm:pl-10 md:pl-20">
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/281/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/282/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/283/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/284/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/295/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/296/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/287/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/288/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/289/400/300" alt="Sunset in the mountains"></swiper-slide>
          <swiper-slide class="scale-up minwidth"><img src="https://picsum.photos/id/280/400/300" alt="Sunset in the mountains"></swiper-slide>
        </swiper>
      </div>
    </div>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css';
import { swiper, swiperSlide, swiperWrapper } from 'vue-awesome-swiper';

import SideBar from './components/Sidebar';
import NavBar from './components/NavBar';

export default {
  data() {
    return {
      user: '',
      active: false,
      lazy: true,
      toggle: false,
      swiperOption: {
        slidesPerView: 3,
        spaceBetween: 5,
      }
    };
  },
  methods: {
    toggleSideBar() {
      this.active = !this.active;
    },
    togglePage() {
      this.toggle = !this.toggle;
    },
    setUser(name) {
      this.user = name;
      this.active = !this.active;
    }
  },
  components: {
    SideBar,
    swiper,
    swiperSlide,
    NavBar
  }
};
</script>

<style>
.scale-up:hover {
  transition: all 400ms cubic-bezier(0.165, 0.84, 0.44, 1);
  transform: scale(1.2);
  z-index: 100;
}

.minwidth {
  min-width: 10rem;
  max-width: 20rem;
}

.max {
  max-width: 100vw;
}
</style>

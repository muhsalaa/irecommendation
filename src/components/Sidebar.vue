<template>
  <nav 
    class="bg-gray-100 fixed content overflow-y-auto w-1/2 sm:w-56 z-10 px-4" 
    :class="{'xxx': !active}"
  >
    <ul>
      <li 
        v-for="(item, id) in dummy" 
        :key="id"
        class="text"
        :class="{'text-active': item.name === user}"
        @click="setUserName(item.name)"
      >
      <span>{{ item.name }}</span>
        
      </li>
    </ul> 
  </nav>
</template>

<script>
export default {
  props: ['active', 'user'],
  data() {
    return {
      dummy: [
        {name: 'Madlyn Desouza'},
        {name: 'Mica Huyser'},
        {name: 'Echo Tekulve'},
        {name: 'Georgeanna Fischetti'},
        {name: 'Vaughn Krogh'},
        {name: 'Carl Loney'},
        {name: 'Mi Laffoon'},
        {name: 'Emmanuel Dickey'},
        {name: 'George Bechard'},
        {name: 'Kenisha Knicely'},
        {name: 'Lorrie Nickols'},
        {name: 'Olimpia Ahumada'},
        {name: 'Anisa Rich'},
        {name: 'Lenora Royal'},
        {name: 'Monty Tarpley'},
        {name: 'Edgardo Sexson'},
        {name: 'Vincenzo No'},
        {name: 'Bertha Angus'},
        {name: 'Latesha Teachout'},
        {name: 'Kendra Crayton'},
        {name: 'Nyla Paiva'},
        {name: 'Wendy Durkee'},
        {name: 'Dudley Farless'},
        {name: 'Pricilla Ashline'},
        {name: 'Margarita Balli'},
        {name: 'Quentin Baillargeon'},
        {name: 'Isiah Tarwater'},
        {name: 'Shan Perino'},
        {name: 'Aleisha Heckathorn'},
        {name: 'Boyd Mullins'},
      ]
    }
  },
  methods: {
    setUserName(name) {
      this.$emit('setUser', name);
    }
  }
}
//:class="[active ? '' : 'hidden']"
</script>

<style>
  .text {
    @apply cursor-pointer text-gray-600 text-base p-1 w-full;
  }

  .text:hover {
    @apply text-black;
    transform: scale(1.1);
    transform: translateX(0.2rem);
    transition-duration: 300ms;
  }

  .text-active {
    @apply text-teal-700 bg-teal-200;
    transform: scale(1.1);
    transform: translateX(0.2rem);
    transition-duration: 300ms;
  }

  .content {
    height: calc(100vh - 4rem);
  }

  .xxx {
    transform: translateX(-20rem);
    transition-duration: 300ms;
  }
</style>

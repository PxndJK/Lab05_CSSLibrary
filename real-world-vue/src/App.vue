<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import { useMessageStore } from '@/stores/message';
import { storeToRefs } from 'pinia';
const store = useMessageStore()
const { message } = storeToRefs(store)
</script>

<template>
  <header class="max-h-screen leading-normal">
    <div id="flashMessage" v-if="message" class="animate-yellowfade">
      <h4 class="text-lg">{{message}}</h4>
    </div>
      <nav class="p-8">
        <RouterLink :to="{ name: 'event-list'}" class="font-bold text-gray-700 hover:text-green-500"> Home </RouterLink>
        <RouterLink :to="{ name: 'event-list2'}" class="font-bold text-gray-700 hover:text-green-500"> Home2 </RouterLink>
        <RouterLink :to="{ name: 'student-list'}" class="font-bold text-gray-700 hover:text-green-500"> Student </RouterLink>
        <RouterLink :to="{ name: 'about'}" class="font-bold text-gray-700 hover:text-green-500"> About </RouterLink>
      </nav>
  </header>

  <RouterView />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

/* nav {
  padding: 30px;
} */

/* nav a {
  font-weight: bold;
  color: #2c3e50;
} */

/* nav a.router-link-exact-active {
  color: #42b983;
} */

/* header {
  line-height: 1.5;
  max-height: 100vh;
} */

/* .logo {
  display: block;
  margin: 0 auto 2rem;
}

h4 {
  font-size: 20px;
} */

@keyframes yellowfade {
  from {
    background: yellow;
  }
  to {
    background: transparent;
  }
}

.animate-yellowfade {
  animation: yellowfade 3s ease-in-out;
}

</style>
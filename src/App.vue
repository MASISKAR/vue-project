<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import {ref} from 'vue'

let count  = ref(0);
console.log(count);
function increment(){
  count.value++;
}
function decrement(){
  count.value--;
}

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="hellooo" />
      <HelloWorld msg="sfxcvcb" />
      <HelloWorld msg="dsfsdfsssss" />
    </div>
  </header>

  <main>
    <TheWelcome />

<button @click="decrement()">-</button>
<span >{{ count }}</span>
<button @click="increment()">+</button>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
export default {
  components: {
    HelloWorld,
    TheWelcome
  },
  data() {
    return {
      count: 0,
      canShowImage: true,
    };
  },
  methods: {
    changeCounter(value) {
      this.count += value;
    },
    resetCounter(){
      this.count = 0;
    },
    hideImage(){
      this.canShowImage = false;
    },
    showImage(){
      this.canShowImage = true;
    }
  }
}
</script>

<template>
  <header>
    <img v-if="canShowImage" alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
    <h3 v-else>The image was hidden!</h3>
    <button @click="showImage()">Show image</button>
<button @click="hideImage()">Hide image</button>

    <div class="wrapper">
      <hello-world v-show="canShowImage" msg="hellooo" />

      <HelloWorld msg="sfxcvcb" />
      <HelloWorld msg="dsfsdfsssss" />
      <TheWelcome />
    </div>
  </header>

  <main>
    <button @click="changeCounter(-10)">-10</button>
    <button @click="changeCounter(-1)">-</button>
    <span>{{ count }}</span>
    <button @click="changeCounter(1)">+</button>
    <button @click="changeCounter(10)">+10</button>
    <button @click="resetCounter()">Reset</button>
<div>The count is:
<span v-if="count === 0">Zero</span>
<span v-else-if="count === 1">One</span>
<span v-else-if="count === 2">Two</span>
<span v-else-if="count === 3">Three</span>
<span v-else>Other</span>

</div>

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

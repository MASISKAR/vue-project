<script>
import Fruits from './components/Fruits.vue';

export default {
  components: {
    Fruits
  },
  data() {
    return {
     email: '',
     isEmailValid: false,
    };
  },
  methods: {
    openEmailPrompt(){
        let email = prompt('Input your email');
        if(!email){
          this.isEmailValid = false;
          return;
        }
        email = email.trim();
        this.email = email;
        console.log(email);
        const isValid = this.checkIsEmailValid(email);
        this.isEmailValid = isValid;
    },
    checkIsEmailValid(email){
      const reg = /^[\w-.]+@([\w-]+\.)+[\w-]{2,4}$/;
     return reg.test(email);
    },
    reset(){
      this.email = '';
      this.isEmailValid = false;
    }
  }
}
</script>

<template>
<main>
<Fruits />


  <button @click="openEmailPrompt()">Input your email</button>
  <button @click="reset()">Reset</button>
<!-- <div v-if="email"> -->
    <!-- <h1 class="green" v-if="isEmailValid">{{ email }}</h1> -->
  <!-- <h1 class="red" v-else>{{ email }}</h1> -->
<!-- </div> -->


  <h1 
  :class="isEmailValid ? 'green' : 'red'"
  v-if="email"
  >{{ email }}</h1>
<h4 v-if="email">{{ `The email is ${isEmailValid ? 'valid': 'invalid'}`}}</h4>

<!-- <h1 :class="{green: isEmailValid}" class="text-center czcds dcds">Conditional class</h1> -->

</main>
</template>

<style scoped>
.red{
  border: 1px solid red;
}

.green{
  border: 1px solid green;
}
</style>

<script>
// import Product from './components/Product.vue';
import Input from './components/Input.vue';
import Hello from './components/Hello.vue'

export default {
  components: {
    // Product,
    Input,
    Hello,
  },
  data() {
    return {
      fruits: [
        {
          name: 'apple',
          price: '3$',
          description: 'Golden apples from Armenia'
        },
        {
          name: 'pear',
          price: '3.4$',
          description: 'Sweet pears'
        },
        {
          name: 'cherry',
          price: '2.6$',
          description: 'Sour red cherries'
        },
        {
          name: 'lemon',
          price: '4$',
          description: 'Big Chinese lemons'
        },
        {
          name: 'banana',
          price: '3.7$',
          description: 'Fresh bananas from Ecuador'
        },
      ],

      name: '',
    }
  },
methods: {
  onSubmit(name){
    this.name = name;
  },
}
}
</script>

<template>
  <main>
<Input @submit-name="onSubmit"/>

<Hello :name="name"/>





<!--  -->
<!-- <ol> -->
  <!-- <li v-for="fruit in fruits" :key="fruit.name"> -->
    <!-- <Product :fruit="fruit" customClass="dicsount"/> -->
  <!-- </li> -->
<!-- </ol> -->
<!--  -->
<!-- <Product  -->
<!-- :fruit="{name: 'apple', price:'2$', description: 'red apples'}"  -->
<!-- customClass="darkred"/> -->
  </main>
</template>

<style>
.dicsount{
  color: goldenrod;
}
.darkred{
  color: darkred;
}
</style>
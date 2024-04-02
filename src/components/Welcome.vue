<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    },
    age: {
      type: Number,
      required: false,
      default: 0,
    },
    surname: String,
  },
  data(){
    return {

    }
  },
  

}
</script>

<template>
  <h3>Hello, my name is {{ name }} {{ surname }}, I am {{ age }} years old!</h3>
  <button>Click me</button>
  <Test :secondName="surname" />
</template>

<script>
export default {
  data() {
    return {
      value: 0,
      rate: 400,
      mode: 'AMD'
    }
  },
  methods: {
    handleInput(event) {
      this.value = event.target.value
    },
    handleInputFocus() {
      if (+this.value === 0) {
        this.value = ''
      }
    },
    toggleMode(){
        if(this.mode === 'AMD'){
            this.mode = 'USD';
        } else {
            this.mode = 'AMD';
        }
        this.value = 0;
    },
  },
  computed: {
    calculatedValue(){
      if(this.mode === 'AMD'){
        return this.value / this.rate;
      }
      return this.value * this.rate;
    },

  },
}
</script>

<template>
  <div v-if="mode === 'AMD'">
    <h4>AMD -> USD</h4>
    <input 
    type="number" 
    v-model="value"
    @focus="handleInputFocus" 
    />
    <input type="number" readonly :value="calculatedValue" />
    <button @click="toggleMode">USD -> AMD</button>
  </div>

  <div v-else>
    <h4>USD -> AMD</h4>
    <input 
    type="number" 
    :value="value" 
    @input="handleInput" 
    @focus="handleInputFocus"
    />
    <input type="number" readonly :value="calculatedValue" />
    <button @click="toggleMode">AMD -> USD</button>
  </div>
</template>

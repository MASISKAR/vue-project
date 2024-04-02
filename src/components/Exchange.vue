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
    }
  }
}
</script>

<template>
  <div v-if="mode === 'AMD'">
    <h4>AMD -> USD</h4>
    <input 
    type="number" 
    :value="value" 
    @input="handleInput" 
    @focus="handleInputFocus" 
    />
    <input type="number" readonly :value="value / rate" />
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
    <input type="number" readonly :value="value * rate" />
    <button @click="toggleMode">AMD -> USD</button>
  </div>
</template>

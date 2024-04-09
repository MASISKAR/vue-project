<script>
import Name from './Name.vue';
import Price from './Price.vue';
import Description from './Description.vue';

export default {
components: {
    Name,
    Price,
    Description
},
props: {
    fruit: {
        type: Object,
        required: true
    },
    customClass: String,
},
methods: {
    onButtonClick(){
        this.$emit('currencyChange');
    }
}
}

</script>

<template>
<div>
    <Name class="red" :value="fruit.name"/> <Price :value="fruit.price" :customClass="customClass"/><button @click="onButtonClick">Change the currency</button> <Description :value="fruit.description"/>
    
</div>
</template>

<style>
.red{
    color: red;
}
</style>
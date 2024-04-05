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
}

}

</script>

<template>
<div>
    <Name class="red" :value="fruit.name"/> <Price :value="fruit.price" :customClass="customClass"/> <Description :value="fruit.description"/>
</div>
</template>

<style>
.red{
    color: red;
}
</style>
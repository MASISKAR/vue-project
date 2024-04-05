<script>
export default {
    props: {
    value: {
        type: String,
        required: true,
    }
}
    
}

</script>

<template>
    <span >{{ value }}</span>
    <!-- <span :style="`color: ${colorValue}`" :class="[{customClass: arr.length > 4 }, 'red', 'row', 'mb-2']">{{ value }}</span> -->
</template>

<style>
/* .red{ */
/*  */
/* } */
/* .dddd{ */
/*  */
/* } */
</style>
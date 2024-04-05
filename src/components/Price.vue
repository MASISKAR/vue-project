<script>
export default {
    props: {
    value: {
        type: String,
        required: true,
    },
    customClass: String,
}
    
}

</script>

<template>
    <span :class="customClass">{{ value }}</span>
</template>


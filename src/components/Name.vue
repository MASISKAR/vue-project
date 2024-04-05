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
<span>{{ value }}</span>
</template>
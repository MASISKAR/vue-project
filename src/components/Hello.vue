<script>
export default {
props: {
    name: String,
}
}


</script>

<template>

    <h1 v-if="name">Hello {{ name }}!</h1>

</template>
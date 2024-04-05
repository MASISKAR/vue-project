<script>
export default {
data(){
    return {
        name: '',
    }
},
methods: {
    onInputChange(event){
       this.name = event.target.value;
    },
    onSubmit(){
        console.log(this.name);
        this.$emit('submitName', this.name);
    }
}
}


</script>

<template>

    <div>
        <input @input="onInputChange" type="text" placeholder="Input your name">
        <button @click="onSubmit">Submit name</button>
    </div>

</template>
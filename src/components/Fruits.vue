<script>

export default {
data(){
    return {
        newFruit: '',
        fruits: ['apple', 'pear', 'cherry', 'peach', 'lemon'],
    };
},
methods: {
    handleInputChange(event){
        this.newFruit = event.target.value;
    },
    addNewFruit(){
        this.fruits.push(this.newFruit);
        this.newFruit = '';
    },
    deleteFruit(fruit){
        this.fruits = this.fruits.filter((f)=> f !== fruit);
    }
}
};

</script>

<template>

    <div>
<ol>
    <li 
    v-for="(fruit, index) of fruits" 
    :key="index+fruit"
    >{{ fruit }}
<button @click="deleteFruit(fruit)">Delete</button>
</li>
</ol>

<input 
type="text"
@input="handleInputChange"
:value="newFruit"
>
<button @click="addNewFruit">Add</button>

    </div>

</template>

<style scoped>

</style>
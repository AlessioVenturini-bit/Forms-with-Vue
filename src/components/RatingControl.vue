<template>
<ul>
    <li :class="{active : modelValue === 'poor'}"><button type="button" @click="activateButton('poor')">Poor</button></li>
    <li :class="{active : modelValue === 'average'}"><button type="button" @click="activateButton('average')">Average</button></li>
    <li :class="{active : modelValue === 'great'}"><button type="button" @click="activateButton('great')">Great</button></li>
</ul>
</template>

<script>
// modelValue and update:modelValue are special prop and methods to use v-model on a component 
export default {
    props:['modelValue'],
    emits:['update:modelValue'],
    methods: {
        activateButton(value) {
            this.$emit('update:modelValue',value)
        }
    },
}
</script>

<style>
ul {
    list-style: none;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0.5rem 0;
    padding: 0;
}

li {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 0.5rem;

}

.active button {
    border-color: orangered;
    color: orangered;
    background-color: peru;

}

li button {
    padding: 1rem;
    border: 1px solid #ccc;
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.5);
    margin: 0 1rem;
}

button {
    border: none;
    margin: none;
    border-radius: 5px;
}
</style>

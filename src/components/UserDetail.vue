<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User name: {{ myName }}</p>
        <p>User name reversed {{ switchName() }}</p>
        <button @click="resetName">Rest Name</button>
        <button @click="resetFn()">Rest Name</button>
    </div>
</template>

<script>
    export default {
        props: {
            myName: {
                type:String,
                required: true,
            },
            resetFn : Function,
        },
        methods:{
            switchName(){
                return this.myName.split("").reverse().join("");
            },
            resetName(){
                this.myName = 'Daniel';
                this.$emit('nameWasReset', this.myName);
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>

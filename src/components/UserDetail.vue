<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>Name is {{ changeName() }}</p>
        <button @click="revertName">Revert name</button>
    </div>
</template>

<script>
    export default {
        props: {
            name : String
        },
        methods: {
            changeName(){
                return this.name.split('').reverse().join('')
            },
            revertName(){
                this.name = 'Max';
                this.$emit('eventReset', this.name);
            }

        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>

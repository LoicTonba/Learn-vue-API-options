<template>
    <div>
        <button @click="increment">Count is: {{  count }}</button> <br><br>
        <button @click="decrement">décompte est: {{  down }}</button>
    </div>
</template>

<script>
export default {
    name: 'EventListeners',
    data() {
        return{
            count: 0,
            down: 0
        }
    },
    methods: {
        increment(){
            this.count++
        },
        decrement(){
            this.down--
        },

    }
}
</script>
<style scoped>

</style>
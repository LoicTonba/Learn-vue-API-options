<template>
    <div>
        <p>----------------ENGLISH--------------</p>
        <button @click="toggle">Toggle</button>
        <h1 v-if="awesome">Vue is awesome!</h1>
        <h1 v-else>Oh no 😥</h1><br><br>
        <p>-----------------FRENCH---------------</p>
        <button @click="bascule">Basculer</button>
        <h1 v-if="genial">Vue est génial!</h1>
        <h1 v-else>Oh non 😥</h1>
    </div>
</template>

<script>
export default {
    name: 'ConditionalRedering',
    data() {
        return {
            awesome: true,
            genial: false
        }
    },
    methods: {
        toggle() {
            this.awesome = !this.awesome;
        },
        bascule() {
            this.genial = !this.genial;
        }

    }
}
</script>

<style scoped>

</style>

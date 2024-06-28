<template>
    <div>
        <input :value="text" type="text" @input="onInput" placeholder="Type here">
        <p>{{ text }}</p> <br><br>
        <input v-model="message" type="text" placeholder="Entrer votre message">
        <p>{{ message }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            text: '',
            message: ''
        }
    },
    methods: {
        onInput(e) {
            this.text = e.target.value
        }
    }
}
</script>

<style scoped>

</style>

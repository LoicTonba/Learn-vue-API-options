<template>
    <div>
        <h1 @click="showConfetti">🎉Congratulations!</h1>
    </div>
</template>

<script>
import JSConfetti from 'js-confetti'

const confetti = new JSConfetti()
export default {
    name: 'Congratu_lations',
    mounted() {
        this.showConfetti()
    },
    methods: {
        showConfetti() {
            confetti.addConfetti()
        }
    }
}
</script>

<style scoped>
    h1 {
        text-align: center;
        cursor: pointer;
        margin-top: 3em;
    }
</style>

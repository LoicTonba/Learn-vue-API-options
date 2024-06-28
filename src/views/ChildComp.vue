<template>
    <div>
        <h1>C'est un commposant composant enfant</h1>
        <h2>{{ msg || 'No props passed yet' }}</h2>
        <slot>Fallback content</slot>
    </div>
</template>

<script>
export default {
    name: 'ChildComp',
    components: {
        
    },
    emits: ['response'],
    created() {
        this.$emit('response', 'hello from child')
    },
    props: {
        msg: String
    }
}
</script>

<style scoped>

</style>

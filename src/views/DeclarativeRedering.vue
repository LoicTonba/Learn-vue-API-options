<template>
    <div>
        <h1>{{ message  }}</h1>
        <h1>{{ message.split('').reverse().join('')  }}</h1>
    </div>
</template>

<script>
export default{
    name: 'DeclarativeRedering',
    data(){
        return{
            message: 'Make me dynamic!'
        }
    }
}
</script>

<style scoped>

</style>
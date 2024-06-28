<template>
    <div>
       <h1 ref="h1ElementRef">Hello</h1>
       <Components>
       </Components>
      
    </div>
</template>

<script>
export default {
    name: 'LifecycleHooks',
    mounted() {
       this.$refs.h1ElementRef.textContent = 'mounted'
    },
    

}
</script>

<style scoped>

</style>

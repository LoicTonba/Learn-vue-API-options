<template>
    <div>
        <ChildComp @response = "(msg) => childMsg = msg">
            This is a some slot content!
        </ChildComp>
        <p>{{ childMsg }}</p>
      
    </div>
</template>

<script>
import ChildComp from './ChildComp.vue'
export default {
    name: 'parentComp',
    components: {
        ChildComp
    },
    data() {
        return {
            greeting: 'Hello from parent',
            childMsg: 'No child msg yet'
        }
    }
}
</script>

<style scoped>

</style>

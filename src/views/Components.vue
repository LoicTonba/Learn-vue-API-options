<template>
    <div>
        <ChildComp :msg="greeting"/>
      
    </div>
</template>

<script>
import ChildComp from './ChildComp.vue'
export default {
    name:'Compo-nents',
    components: {
        ChildComp
    },
    data() {
        return {
            greeting: 'Hello from parent'
        }
    }
}
</script>



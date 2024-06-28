<template>
   <div>
    <div class="english">
        <h1>----------------------------ENGLISH------------------------</h1>
        <p>Todo id: {{ todoId }}</p>
        <button @click="todoId++" :disabled="!todoData">Fetch next todo</button>
        <p v-if="!todoData">Loading...</p>
        <pre v-else>{{ todoData }}</pre>
    </div><br><br>
    <div class="french">
        <h1>----------------------------FRENCH------------------------</h1>
        <p>Identifiant de la tache: {{ tacheId }}</p>
        <button @click="tacheId++" :disabled="!tacheDonnee">Récupérer la tache suivante</button>
        <p v-if="!tacheDonnee">Téléchargement...</p>
        <p v-else>{{ tacheDonnee }}</p>
    </div>
   </div>
</template>

<script>
export default {
    name: 'WatChers',
    data() {
        return {
            todoId: 1,
            todoData: null,
            tacheId: 1,
            tacheDonnee: null
        }
    },
    methods: {
        async fetchData() {
            this.todoData = null
            const res = await fetch(
                `https://jsonplaceholder.typicode.com/todos/${this.todoId}`
            )
            this.todoData = await res.json()
        },

        async recupererDonnee() {
            this.tacheDonnee = null
            const resultat = await fetch(
                `https://jsonplaceholder.typicode.com/todos/${this.tacheId}`
            )
            this.tacheDonnee = await resultat.json()
        }
    },
    mounted() {
        this.fetchData()
        this.recupererDonnee()
    },
    watch: {
        todoId() {
            this.fetchData()
        },
        tacheId() {
            this.recupererDonnee()
        }
    }
}
</script>

<style scoped>
.english{
    background: rgba(207, 238, 238, 0.6);
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 0 15px rgba(207, 238, 238, 0.6)
}
.french{
    background: rgba(171, 211, 154, 0.6);
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 0 15px rgba(32, 34, 34, 0.6)
}
</style>

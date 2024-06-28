<template>
    <div>
        <P>--------------------ENGLISH---------------------------------</P>
        <form @submit.prevent="addTodo">
            <input v-model="newTodo" required placeholder="new todo">
            <button>Add Todo</button>
        </form>
        <ul>
            <li v-for="todo in todos" :key="todo.id">
                {{ todo.text }}
                <button @click="removeTodo(todo)">X</button>
            </li>
        </ul><br><br>
        <P>--------------------FRENCH---------------------------------</P>
        <form v-on:submit.prevent="ajouterTache">
            <input v-model="nouvelletache" required type="text" placeholder="Entrer la tache">
            <button>Ajouter Tache</button>
        </form>
        <ul>
            <li v-for="tache in listeTache" :key="tache.unique">{{ tache.text }}
             <button v-on:click="supprimerTache(tache)">X</button>
            </li>
        </ul>
    </div>
</template>

<script>
// give each todo a unique id
let id = 0
let unique = 0
export default {
    name: 'ListRendering',
    data() {
        return {
            newTodo: '',
            todos: [
                {id: id++, text: 'Learn HTML & CSS'},
                {id: id++, text: 'Learn Javascript'},
                {id: id++, text: 'Learn Vue'}
            ],
            nouvelletache: '',
            listeTache: [
                {unique: unique++, text: 'Apprendre le rendu déclaratif'},
                {unique: unique++, text: 'Apprendre les Liaisons d\'attributs'},
                {unique: unique++, text: 'Apprendre les écouteurs d\'évènements'},
                {unique: unique++, text: 'Apprendre les Liaisons de formulaire'},
                {unique: unique++, text: 'Apprendre le rendu conditionnel'},
                {unique: unique++, text: 'Apprendre le rendu de Liste'},
                {unique: unique++, text: 'Apprendre la propriété calculée'},
                {unique: unique++, text: 'Apprendre le cycle de vie et référence de modèle'},
                {unique: unique++, text: 'Apprendre l\'observateur'},
                {unique: unique++, text: 'Apprendre les composants'},
                {unique: unique++, text: 'Apprendre les accessoires'},
                {unique: unique++, text: 'Apprendre les Emets'},
                {unique: unique++, text: 'Apprendre les machines à sous'},
           
            ]
        }
    },
    methods: {
        addTodo() {
            this.todos.push({ id: id++, text: this.newTodo })
            this.newTodo = ''
        },
        removeTodo(todo) {
            this.todos = this.todos.filter((t) => t !== todo)
        },

        ajouterTache() {
            this.listeTache.push({unique: unique++, text: this.nouvelletache})
            this.nouvelletache = ''
        },
        supprimerTache(tache) {
            this.listeTache = this.listeTache.filter((t) => t !== tache)

        }
    }
}
</script>

<style scoped>

</style>

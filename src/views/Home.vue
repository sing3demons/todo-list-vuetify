<template>
    <div>
        <v-container>
            <todo-add v-on:onSubmit="addTask" />
            <TodoList :todos="reversTodo" @itemID="removeItem" />
        </v-container>
    </div>
</template>

<script>
import TodoAdd from '../components/TodoAdd.vue'
import TodoList from '../components/TodoList.vue'
import axios from 'axios'

export default {
    name: 'Home',

    components: { TodoList, TodoAdd },
    async mounted() {
        let { data } = await axios.get('https://jsonplaceholder.typicode.com/todos')
        this.todos = data
    },
    computed: {
        reversTodo() {
            return this.todos.slice().reverse()
        }
    },
    methods: {
        async addTask(title) {
            let { data } = await axios.post('https://jsonplaceholder.typicode.com/todos', { title })
            this.todos.push(data)
        },
        removeItem(id) {
            // this.todos.splice(id, 1) == index

            this.todos = this.todos.filter(item => item.id !== id)
        }
    },
    data: () => ({
        taskText: '',
        todos: [
            // { id: 1, title: 'Vue', completed: true },
            // { id: 2, title: 'React', completed: false }
        ]
    })
}
</script>

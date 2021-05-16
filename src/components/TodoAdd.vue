<template>
    <v-row>
        <v-col cols="11">
            <v-text-field name="name" label="Task" @keyup.enter="addTask" v-model="taskText" />
        </v-col>
        <v-col>
            <v-btn @click="addTask" block color="success">Add</v-btn>
        </v-col>
    </v-row>
</template>

<script>
export default {
    methods: {
        addTask() {
            this.$emit('onSubmit', this.taskText)
            this.taskText = ''
        }
    },
    data() {
        return {
            taskText: ''
        }
    }
}
</script>

<style>
</style>
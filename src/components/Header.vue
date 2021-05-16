<template>
    <v-app-bar app color="primary" dark>
        <div class="d-flex align-center">
            <v-img
                alt="Todo List"
                class="shrink mr-2"
                contain
                src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
                transition="scale-transition"
                width="40"
            />
            <v-btn target="_blank" text>
                <span class="mr-2">Todo List</span>
            </v-btn>
        </div>

        <v-spacer></v-spacer>

        <v-btn target="_blank" text>
            <span class="mr-2">Latest Release</span>
            <v-icon>mdi-open-in-new</v-icon>
        </v-btn>
    </v-app-bar>
</template>

<script>
export default {}
</script>

<style>
</style>
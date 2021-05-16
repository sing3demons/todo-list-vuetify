<template>
    <v-card>
        <v-card-title primary-title>
            <v-container>
                <v-row class="d-flex flex-row align-center" v-for="(item) in todos" :key="item.id">
                    <v-col cols="12" class="d-flex flex-row align-center pa-0">
                        <v-checkbox v-model="item.completed"></v-checkbox>
                        {{item.title}}
                        <v-spacer />
                        <v-btn @click="$emit('itemID',item.id)" color="error">x</v-btn>
                    </v-col>
                    <v-col cols="12">
                        <v-divider />
                    </v-col>
                </v-row>
            </v-container>
        </v-card-title>
    </v-card>
</template>

<script>
export default {
    props: ['todos'],
    methods: {},
    data() {
        return {}
    }
}
</script>

<style>
</style>
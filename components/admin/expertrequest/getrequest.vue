<template>
    <div>
        <div v-for="doc in docss" :key="doc.id" class="d-flex">
            <!-- <button @click="$emit('confirmdoc', doc.expert_id, doc.result)">x</button> -->
            <p class="m-2">{{ doc.id }}</p>
            <!-- <h4>{{ doc.expert_id }}</h4> -->
            <p class="m-2">{{ doc.description }}</p>
            <p class="m-2">{{ doc.result }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['docss']
    }
</script>

<style scoped>

</style>
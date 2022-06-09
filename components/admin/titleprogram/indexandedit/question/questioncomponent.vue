<template>
    <div>
        <div v-for="doc in docss.data" :key="doc.id" >
            <!-- <button @click="$emit('confirmdoc', doc.expert_id, doc.result)">x</button> -->
            <!-- <p class="m-2">{{ doc.data }}</p> -->
            <h4>{{ doc.title_program_id }}</h4>
            <!-- <p class="m-2">{{ doc.description }}</p> -->
            <!-- <p class="m-2">{{ doc.result }}</p> -->
        </div>
    </div>
</template>

<script>
    export default {
        props: ['docss']
    }
        // console.log(doc.data)
</script>

<style scoped>

</style>
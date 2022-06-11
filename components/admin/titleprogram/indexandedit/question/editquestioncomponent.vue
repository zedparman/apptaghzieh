<template>
    <div>
        <div v-for="doc in docsss" :key="doc.id">
            {{ doc.id }}
            {{ doc.title_question }}
        </div>
    </div>
</template>

<script>
    export default {
        props: ['docsss']
    }
</script>

<style scoped>

</style>
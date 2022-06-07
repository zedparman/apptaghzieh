<template>
    <div>
        <h1>admin</h1>
        <confirmexpert />
        <br>
        <changeExpertRequest />
        <br>
        <hr>
        <InsertTitleProgram />
    </div>
</template>

<script>
import changeExpertRequest from '@/components/admin/expertrequest/changeExpertRequest.vue';
import InsertTitleProgram from '@/components/admin/titleprogram/InsertTitleProgram.vue';
import confirmexpert from '@/components/admin/expertmanagement/confirmexpert.vue';
    export default {
        components: {
            changeExpertRequest,
            InsertTitleProgram,
            confirmexpert,
        },
    }
</script>

<style scoped>
*{
    text-align: center;
}
</style>
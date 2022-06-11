<template>
  <div class="m-4">
    <h4>مشاده سوالات مربوط به یک رژیم با ارسال آی دی رژیم در نوارد ادرس   14</h4>



  <form @submit.prevent="getDoc">
    <input type="text" v-model="title_program_id">
    <button type="subnit">submit</button>
  </form>
  <div v-for="doc in docs.data" :key="doc.id">
    {{ doc.title_program_id }}
    {{ doc.title_question }}
  </div>

    <editquestion :docss="docs"/>

  </div>
</template>

<script>
import questioncomponent from './questioncomponent.vue';
import editquestion from './editquestion.vue';
export default {
  components: { questioncomponent },
  components: { editquestion },
  data() {
    return {
      docs: [],
      "title_program_id": "37",
    };
  },
  mounted() {
    this.getDoc();
  },
  methods: {
    async getDoc() {
      let res = await this.$axios.get(
        `http://95.217.96.131:8080/api/admin/index-question/${this.title_program_id}`,
        {
          headers: {
            Authorization: "Bearer " + localStorage.getItem("token"),
          },
        }
      );
            this.docs = res;
            console.log("res: ", res)
    },
  },
}
</script>

<style scoped></style>

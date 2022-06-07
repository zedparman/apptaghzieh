<template>
  <div class="m-4">
    <h4>مشاده سوالات مربوط به یک رژیم با ارسال آی دی رژیم در نوارد ادرس   14</h4>


    <ul>
      <li v-for="doc in docs" :key="doc.id" class="d-flex">
        <!-- <h1>{{ docs.data.data.mobile }}</h1> -->
        <p class="m-2">{{ doc.title_question }}</p><br>
        <!-- <p class="m-2">{{ doc.options_question }}</p> -->
      </li>
    </ul>  


  </div>
</template>

<script>
export default {
  data() {
    return {
      docs: []
    };
  },
  mounted() {
    this.getDoc();
  },
  methods: {
    async getDoc() {
      let res = await this.$axios.get(
        "http://95.217.96.131:8080/api/admin/index-question/37",
        {
          headers: {
            Authorization: "Bearer " + localStorage.getItem("token"),
          },
        }
      );
            this.docs = res.data.data;
            console.log(res.data);
    },
  },
}
</script>

<style scoped></style>

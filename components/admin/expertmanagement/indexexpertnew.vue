<template>
  <div>
    <h4>مشاهده کارشناسان تایید نشده و جدید05</h4>
  

    <div v-for="doc in docs" :key="doc.id" class="d-flex">
      <p class="m-2">{{ doc.id }}</p>
      <p class="m-2">{{ doc.name }}</p>
      <p class="m-2">{{ doc.mobile }}</p>
      <p class="m-2">{{ doc.is_active }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['docss'],
  
  data() {
    return {
      docs: [],
    };
  },
  mounted() {
    this.getDoc();
  },
  methods: {
    async getDoc() {
      let rs = await this.$axios.get(
        "http://95.217.96.131:8080/api/admin/index-expert/new",
        {
          headers: {
            Authorization: "Bearer " + localStorage.getItem("token"),
          },
        }
      );
      this.docs = rs.data.data;
      console.log(rs.data);
    },
  },
};
</script>

<style scoped>

</style>

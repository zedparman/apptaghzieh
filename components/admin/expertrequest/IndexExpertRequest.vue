<template>
  <div>
    <p>لیست درخواست کارشناسان برای آنلاین یا آفلاین شدن</p>
    <getrequest :docss="docs.data"/>
  </div>
</template>

<script>
import getrequest from '@/components/admin/expertrequest/getrequest.vue';
export default {
  components: {
    getrequest,
  },
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
        "http://95.217.96.131:8080/api/admin/index-expert-request/all",
        {
          headers: {
            Authorization: "Bearer " + localStorage.getItem("token"),
          },
        }
      );
      this.docs = rs.data.data;
      console.log(rs.data.data);
    },
  },
};
</script>

<style scoped></style>

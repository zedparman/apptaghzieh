<template>
  <div class="main-content">
    <h1>me</h1>
    نام: {{ docs.name }}<hr>
    جنسیت: {{ docs.gender }}<hr>
    تصویر: {{ docs.avatar }}<hr>
    شماره موبایل: {{ docs.mobile }}<hr>
    شهر: {{ docs.city }}<hr>
    نوع: {{ docs.type }}<hr>
    وضعیت کاربر: {{ docs.is_admin }}<hr>
    فعال: {{ docs.is_active }}<hr>
    آخرین سفارش: {{ docs.last_order }}
    <!-- <ul>
      <li v-for="doc in docs" :key="doc.id">
        <h1>{{ docs.data.mobile }}</h1>
        <h1>{{ docs.data.last_order }}</h1>
        <h1>{{ docs.data.avatar }}</h1>
      </li>
    </ul> -->





  
  </div>
</template>

<script>
export default {
  
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
      let rs = await this.$axios.get("http://95.217.96.131:8080/api/me",
          {
            headers: {
              Authorization: "Bearer " + localStorage.getItem("token"),
            },
          });
      this.docs = rs.data.data;
      console.log(rs);
      // console.log(docs)
    },
  },
};
</script>

<style scoped>
*{
  direction: rtl;
  text-align: right;
}
</style>
<template>
  <div class="m-4">
    <h4>مشاهده عنوان های رژیم11</h4>
    <!-- {{ doc }} -->

    <ul>
      <li v-for="doc in docs" :key="doc.id" class="d-flex">
        <!-- <h1>{{ docs.data.data.mobile }}</h1> -->
        <p class="m-2">{{ doc.id }}</p>
        <p class="m-2">{{ doc.name }}</p>
      </li>
    </ul>
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
      let rs = await this.$axios.get(
        "http://95.217.96.131:8080/api/admin/index-titleprogram/",
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

<style scoped></style>

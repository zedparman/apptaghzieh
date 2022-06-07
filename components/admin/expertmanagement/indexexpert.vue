<template>
  <div class="expertlist border border-success mb-5 p-3 px-5">
    <div id="first">
      <h4>مشاهده کلیه کارشناسان  04</h4>
      <ul>
        <li v-for="doc in docs" :key="doc.id"  class="d-flex"  :class="{inactive:!doc.is_active}">
          <input type="checkbox" @change="markComplete" class="m-3"><p class="m-2">{{ doc.id }}</p>
          <p class="m-2">{{ doc.name }}</p>
          <p class="m-2">{{ doc.id }}</p>
          <p class="m-2">{{ doc.is_active }}</p>
          <button @click="$emit('doc-del', doc.id, doc.is_active)">x</button>
        </li>
      </ul>
    </div>

    <!-- <div id="second">
      <indexexpertnew :docss="docs.data" />
      <confirmexpert :docss="docs.data" />
    </div> -->
  </div>
</template>

<script>
// import indexexpertnew from "@/components/admin/expermanagement/indexexpertnew.vue";
// import confirmexpert from "@/components/admin/expermanagement/confirmexpert.vue";
export default {
  // components: {
  //   indexexpertnew,
  //   confirmexpert,
  // },
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
      let res = await this.$axios.get(
        "http://95.217.96.131:8080/api/admin/index-expert",
        {
          headers: {
            Authorization: "Bearer " + localStorage.getItem("token"),
          },
        }
      );
      this.docs = res.data.data;
      console.log(res.data);
    },
    async markComplete(){
      console.log(123)
    }
  },
};
</script>

<style scoped>
* {
  list-style: none;
}

.expertlist {
  display: flex;
  height: 500px;
}

.expertlist #first {
  flex-basis: 50%;
  align-self: center;
}
.expertlist #second {
  flex-basis: 50%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

.inactive{
  border: solid red;
  /* display: none; */
}


</style>

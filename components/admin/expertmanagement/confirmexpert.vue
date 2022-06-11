<template>
  <div class="container my-4 d-flex">
    <div class="second">
      <indexexpert />
    </div>
    <div class="first m-4 p-4">
      <h4>تایید یا غیرفعال سازی کارشناس 0 غیر فعال و 1 فعال06</h4>
      <form @submit="handlePhoneNumber">
        <input
          type="text"
          class="form-control mb-2"
          v-model="expert_id"
          placeholder="expert_id"
        />
        <input
          type="text"
          class="form-control mb-2"
          v-model="active"
          placeholder="active"
        />
        <input class="btn btn-primary w-100" type="submit" value="submit" />
      </form>
      <indexexpertnew class="mt-4"/>
    </div>
    <!-- <h1>{{sendid}}</h1> -->
    <!-- <div v-for="doc in docs" :key="doc.id">
      {{ doc }}
    </div> -->
    <!-- {{ sendi }} -->
  </div>
</template>

<script>
import indexexpert from "@/components/admin/expertmanagement/indexexpert.vue";
import indexexpertnew from "@/components/admin/expertmanagement/indexexpertnew.vue";
import axios from "axios";
export default {
  components: {
    indexexpert,
    indexexpertnew,
  },
  // props: ['docs'],
  data() {
    return {
      expert_id: "",
      active: "",
    };
  },
  methods: {
    async handlePhoneNumber() {
      try {
        let response = await axios.post(
          "http://95.217.96.131:8080/api/admin/confirm-expert",
          {
            expert_id: this.expert_id,
            active: this.active,
          },
          {
            headers: {
              Authorization: "Bearer " + localStorage.getItem("token"),
            },
          }
        );
        console.log(response);
        const cred = localStorage.getItem("token");
      } catch (error) {
        console.log(error);
      }
      // console.log(sendid.data.data)
    },
  },
};
</script>

<style scoped></style>

<template>
  <div class="main">
    <div class="first">
      <IndexExpertRequest />
    </div>
    <div class="my-4 second">
      <p>تایید یا رد درخواست کارشناس مبنی بر آنلاین و یا آفلاین بودن</p>
      <form @submit.prevent="handlePhoneNumber">
        <input
          type="text"
          class="form-control mb-2"
          v-model="request_id"
          placeholder="request_id"
        />
        <input
          type="text"
          class="form-control mb-2"
          v-model="result"
          placeholder="result"
        />
        <input class="btn btn-primary w-100" type="submit" value="submit" />
      </form>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import IndexExpertRequest from "@/components/admin/expertrequest/IndexExpertRequest.vue";
export default {
  components: {
    IndexExpertRequest,
  },
  data() {
    return {
      request_id: "",
      result: "",
    };
  },
  methods: {
    async handlePhoneNumber() {
      try {
        let response = await axios.post(
          "http://95.217.96.131:8080/api/admin/change-expert-request",
          {
            request_id: this.request_id,
            result: this.result,
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
    },
  },
};
</script>

<style scoped>
* {
  text-align: center;
}

.main {
  display: flex;
  justify-content: space-between;
}
.first {
  flex-basis: 50%;
}
.second {
  flex-basis: 50%;
}
</style>

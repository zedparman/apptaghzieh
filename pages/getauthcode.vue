<template>
  <div>
    <div class="container form-group main">
      <div>
        <h1>title</h1>
      </div>
      <div>
        <!-- <h1>{{ phone_number }}</h1>
        <h1>{{ sms_token }}</h1> -->

        <form @submit.prevent="handleDoctorVerify">
          <!-- <h1>{{ phone_number }}</h1> -->
          <!-- <input
            type="text"
            class="form-control mb-2"
            v-model="mobile"
            placeholder="mobile"
          /> -->
          <input
            type="text"
            class="form-control mb-2"
            v-model="code"
            placeholder="code"
          />
          <!-- <input
            type="text"
            class="form-control mb-2"
            v-model="level"
            placeholder="level"
          /> -->
          <input class="btn btn-primary w-100" type="submit" value="submit" />
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      mobile: "",
      code: "",
      level: 1
    //   token_type: "DOCTOR_TOKEN",
    };
  },
  methods: {
    async handleDoctorVerify() {
      let response = await axios.post(
        "http://95.217.96.131:8080/api/getauthcode",
        {
          mobile: this.mobile,
        //   token_type: "DOCTOR_TOKEN",
          code: this.code,
          level: this.level
        }
      );
      console.log(response);
      this.$router.push("/me");
      localStorage.setItem("code", this.code);
      localStorage.setItem('token', response.data.access_token)
      console.log(response.data)
      this.mobile = "";
    },
  },
  mounted() {
    if (process.client) {
      this.mobile = localStorage.getItem("mobile");
      // this.code = localStorage.getItem("code");
    }
  },
};
</script>
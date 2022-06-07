<template>
    <div class="container my-4">
      <h4>درج سوالات تخصصی  تایتل پروگرم آیدی مربوط به ایندگس تایتل پروگرم   ایز نسسری  0 اجباری 1 اختیاری   ایز دیوریشن سوالات دوره ای هست یا نیست0 اجباری  1 اختیاری   13</h4>
        <form @submit.prevent="handlePhoneNumber">
          <input
            type="text"
            class="form-control mb-2"
            v-model="title_program_id"
            placeholder="title_program_id"
          />
          <input
            type="text"
            class="form-control mb-2"
            v-model="title_question"
            placeholder="title_question"
          />
          <input
            type="text"
            class="form-control mb-2"
            v-model="options_question"
            placeholder="options_question"
          />
          <input
            type="text"
            class="form-control mb-2"
            v-model="type_of_question"
            placeholder="type_of_question"
          />
          <input
            type="text"
            class="form-control mb-2"
            v-model="is_public"
            placeholder="is_public"
          />
          <input
            type="text"
            class="form-control mb-2"
            v-model="is_necessary"
            placeholder="is_necessary"
          />
          <input
            type="text"
            class="form-control mb-2"
            v-model="is_duration"
            placeholder="is_duration"
          />
          <input class="btn btn-primary w-100" type="submit" value="submit" />
        </form>
    </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      title_program_id: "",
      title_question: "",
      options_question: "",
      type_of_question: "",
      is_public: "",
      is_necessary: "",
      is_duration: ""
    };
  },
  methods: {
    async handlePhoneNumber() {
      try {
        let response = await axios.post("http://95.217.96.131:8080/api/admin/insert-question", {
        title_program_id: this.title_program_id,
        title_question: this.title_question,
        options_question: this.options_question,
        type_of_question: this.type_of_question,
        is_public: this.is_public,
        is_necessary: this.is_necessary,
        is_duration: this.is_duration
      },
          {
            headers: {
              Authorization: "Bearer " + localStorage.getItem("token"),
            },
          });
        console.log(response);
        const cred = localStorage.getItem("token");
      } catch (error) {
        console.log(error);
      }
    }
  }
};
</script>

<style scoped>

</style>
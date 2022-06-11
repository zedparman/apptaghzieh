<template>
    <div class="container my-4">
      <h4>ویرایش پرسش ها</h4>
        <form @submit="handlePhoneNumber">
          <input
            type="text"
            class="form-control mb-2"
            v-model="question_id"
            placeholder="question_id"
          />
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
            v-model="photo1"
            placeholder="photo1"
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




        <div v-for="doc in docss.data" :key="doc.id" class="d-flex">
            <!-- <button @click="$emit('confirmdoc', doc.expert_id, doc.result)">x</button> -->
            <!-- <p class="m-2">{{ doc }}</p> -->
            <p class="m-2">{{ doc.title_program_id }}</p>
            <p class="m-2">{{ doc.title_question }}</p>
            <p class="m-2">{{ doc.options_question }}</p>
            <p class="m-2">{{ doc.title_program_id }}</p>
            <p class="m-2">{{ doc.updated_at }}</p>
            <!-- <h4>{{ doc.expert_id }}</h4> -->
            <!-- <p class="m-2">{{ doc.description }}</p>
            <p class="m-2">{{ doc.result }}</p> -->
        </div>

    <editquestioncomponent :docsss="docss.data"/>

    </div>
</template>

<script>
import editquestioncomponent from '@/components/admin/titleprogram/indexandedit/question/editquestioncomponent.vue';
import axios from "axios";
export default {
  components: {
    editquestioncomponent,
  },
  props: ['docss'],
  data() {
    return {
      question_id: "",
      title_program_id: "",
      title_question: "",
      options_question: "",
      type_of_question: "",
      photo1: "",
      is_necessary: "",
      is_duration: ""
    };
  },
  methods: {
    async handlePhoneNumber() {
      try {
        let response = await axios.post("http://95.217.96.131:8080/api/admin/edit-question", {
        question_id: this.question_id,
        title_program_id: this.title_program_id,
        title_question: this.title_question,
        options_question: this.options_question,
        type_of_question: this.type_of_question,
        photo1: this.photo1,
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
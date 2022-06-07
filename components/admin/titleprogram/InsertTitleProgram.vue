<template>
  <div>
      <div class="main">
    <div class="first">
      <IndexTitleProgram />
    </div>
    

      <insertquestion class="second"/>
    


  </div>

  <div class="main">
  <IndexQuestion class="first"/>


      <div class="second">
        <div class="my-4">
      <h4>درج عنوان رژیم جدید 0 یعنی اتوماتیک 1 یعنی دستی 10</h4>
      <form @submit.prevent="handlePhoneNumber">
        <input
          type="text"
          class="form-control mb-2"
          v-model="title_program"
          placeholder="title_program"
        />
        <input
          type="text"
          class="form-control mb-2"
          v-model="diet_type"
          placeholder="diet_type"
        />
        <input
          type="text"
          class="form-control mb-2"
          v-model="image"
          placeholder="image"
        />
        <input class="btn btn-primary w-100" type="submit" value="submit" />
      </form>
    </div>
    <div>
        <EditTitleProgram />
    </div>
    </div>



  </div>
<hr>
<br>
<br>
<br>
  </div>
</template>

<script>
import axios from "axios";
import IndexTitleProgram from "@/components/admin/titleprogram/indexandedit/IndexTitleProgram.vue";
import EditTitleProgram from "@/components/admin/titleprogram/indexandedit/EditTitleProgram.vue";
import IndexQuestion from "@/components/admin/titleprogram/indexandedit/question/IndexQuestion.vue";
import insertquestion from "@/components/admin/titleprogram/indexandedit/question/insertquestion.vue";
export default {
  components: {
    IndexTitleProgram,
    EditTitleProgram,
    IndexQuestion,
    insertquestion,
  },
  data() {
    return {
      title_program: "",
      diet_type: "",
      image: "",
    };
  },
  methods: {
    async handlePhoneNumber() {
      try {
        let response = await axios.post(
          "http://95.217.96.131:8080/api/admin/insert-titleprogram",
          {
            title_program: this.title_program,
            diet_type: this.diet_type,
            image: this.image,
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

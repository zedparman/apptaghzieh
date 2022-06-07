<template>
  <div class="container my-4">
    <h4>ویرایش عنوان رژیم12</h4>
    <form @submit.prevent="handlePhoneNumber">
      <input
        type="text"
        class="form-control mb-2"
        v-model="name"
        placeholder="name"
      />
      <input
        type="text"
        class="form-control mb-2"
        v-model="tile_program_id"
        placeholder="tile_program_id"
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
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      name: "",
      tile_program_id: "",
      diet_type: "",
      image: "",
    };
  },
  methods: {
    async handlePhoneNumber() {
      try {
        let response = await axios.post(
          "http://95.217.96.131:8080/api/admin/edit-titleprogram/",
          {
            name: this.name,
            tile_program_id: this.tile_program_id,
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

<style scoped></style>

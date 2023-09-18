<template>
  <form class="form">
    <div class="form-group">
      <label class="form-label" for="url"> Video Url </label>
      <input v-model="videoUrl" class="form-input" type="url" id="url" />
    </div>
    <div class="form-group">
      <label class="form-label" for="name"> Video Name </label>
      <input v-model="videoName" class="form-input" type="text" id="name" />
    </div>
    <button @click="addVideo" class="form-button">Add Video</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      videoUrl: "www",
      videoName: "mohammed dabour is the best programmer",
    };
  },
  methods: {
    addVideo($event) {
      console.log("vedio added");
      $event.preventDefault();
      this.$emit("addVideo", {
        url: this.videoUrl,
        name: this.videoName,
      });
    },
  },
};
</script>
<style scoped>
.form {
  background: linear-gradient(80deg, lightblue, lightgreen);
  padding: 1rem;
  text-align: center;
}
.form-input {
  background: none;
  border: none;
  outline: none;
  border-bottom: 1px solid yellow;
  font-size: 1.2rem;
  font-weight: bold;
}
form-label {
  font-size: 1.1rem;
  font-weight: bold;
}
.form-button {
  background: yellow;
  padding: 0.4rem 0.6rem;
  border: none;
  border-radius: 8px;
  font-weight: bold;
  font-size: 1.1rem;
}
.form-button:hover {
  cursor: pointer;
  filter: brightness(70%);
}
.form-group {
  margin: 1rem 0;
}
</style>

<template>
  <h1>Welcome in my project "My videos app"</h1>
  <videos-form @addVideo="addVideo"></videos-form>
</template>

<script>
import videosForm from "./components/videosForm.vue";
export default {
  name: "App",
  components: {
    videosForm,
  },
  methods: {
    addVideo() {},
  },
};
</script>

<style>
#app {
  margin: 0;
  padding: 0;
}
</style>

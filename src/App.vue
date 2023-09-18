<template>
  <div>
    <h1>Welcome in my project "My videos app"</h1>
    <videos-form @addVideo="addVideo"></videos-form>
    <!-- <div v-for="video in videos" :key="video.url">{{ video.name }} - {{ video.url }}</div>
    {{ videos }} -->
    <videos-table :videos="videos"></videos-table>
  </div>
</template>

<script>
import VideosForm from "./components/VideosForm.vue";
import VideosTable from "./components/VideosTable.vue";
export default {
  name: "App",
  components: {
    VideosForm,
    VideosTable,
  },
  data() {
    return {
      videos: [
        {
          name: "Learn VueJs",
          url: "www.vuejs.com",
        },
      ],
    };
  },
  methods: {
    addVideo(payload) {
      const { name, url } = payload;
      console.log(name, url);
      this.videos.push({
        name: name,
        url: url,
      });
    },
  },
};
</script>

<style>
#app {
  margin: 0;
  padding: 0;
}
</style>

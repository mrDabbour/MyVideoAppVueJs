<template>
  <div>
    <videos-form @addVideo="addVideo"></videos-form>
    <page-section title="My Videos">
      <template v-slot:content>
        <videos-table @deleteVideo="deleteVideo" :videos="videos"></videos-table>
      </template>
      <template v-slot:controls>
        <VideosControl></VideosControl>
        <!-- Corrected component name -->
      </template>
    </page-section>
  </div>
</template>
<script>
import VideosForm from "./components/VideosForm.vue";
import VideosTable from "./components/VideosTable.vue";
import VideosControl from "./components/VideosControl.vue";
import PageSection from "./components/PageSection.vue";

export default {
  name: "App",
  components: {
    VideosForm,
    VideosTable,
    PageSection,
    VideosControl,
  },
  data() {
    return {
      videos: [
        {
          name: "Learn VueJs",
          url: "www.Vuejs.com",
        },
        {
          name: "Learn Angular",
          url: "www.Angular.com",
        },
        {
          name: "Learn NodeJs",
          url: "www.NodeJs.com",
        },
        {
          name: "Learn ReactJs",
          url: "www.ReactJs.com",
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
    deleteVideo(video) {
      console.log(video);
      this.videos = this.videos.filter(
        (v) => v.name !== video.name && v.url !== video.url
      );
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

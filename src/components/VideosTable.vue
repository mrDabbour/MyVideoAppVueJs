<template>
  <h1>Videos Table Page</h1>

  <table class="table">
    <tr class="table-headRow">
      <th class="table-headCell">Id</th>
      <th class="table-headCell">Name</th>
      <th class="table-headCell">URL</th>
      <th class="table-headCell">Delete</th>
    </tr>
    <tr class="table-row" v-for="video in videos" :key="video.url">
      <th class="table-cell">{{ video.id }}</th>
      <th class="table-cell">{{ video.name }}</th>
      <th class="table-cell">{{ video.url }}</th>
      <th class="table-cell">X</th>
    </tr>
  </table>
</template>

<script>
export default {
  props: {
    videos: {
      type: Array,
      required: true,
    },
  },
};
</script>
<style scoped>
.table {
  width: 100%;
  border-collapse: separate;
}

.table-row .table-headRow {
  text-align: left;
}

.table-headCell {
  background: #e5e5e5;
}

.table-cell .table-headCell {
  padding: 0.4rem;
}
.table-cell:last-center {
  color: tomato;
  text-align: center;
  font-weight: bold;
  cursor: pointer;
}
</style>

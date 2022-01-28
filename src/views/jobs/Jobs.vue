<template>
  <div class="job">
    <h1>{{ title }}</h1>
    <div v-if="jobs.length">
      <div v-for="job in jobs" :key="job.id" class="job">
        <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">
          <h3>{{ job.name }}</h3>
        </router-link>
      </div>
    </div>
    <div v-else>
      <p>Loading Jobs...</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "List of jobs",
      jobs: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/jobs")
      .then((res) => res.json())
      .then((data) => (this.jobs = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style>
.job h3 {
  background: #f4f4f4;
  padding: 20px;
  border-radius: 10px;
  margin: 10px auto;
  max-width: 600px;
  cursor: pointer;
  color: #444;
}
.job h3:hover {
  background: #ddd;
}
.job a {
  text-decoration: none;
}
</style>

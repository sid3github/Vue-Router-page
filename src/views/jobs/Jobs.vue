<template>
  <div class="job">
    <h1>{{ title }}</h1>
    <div v-for="job in jobs" :key="job.id" class="job">
      <router-link :to="{ name: 'JobDetails', params: { id: job.id } }">
        <h3>{{ job.name }}</h3>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "List of jobs",
      jobs: [
        {
          id: 1,
          name: "HR Manager",
          details:
            "HR Manager is the go-to person for all employee-related issues. This means that your HR Manager duties will involve managing activities such as job design, recruitment, employee relations, performance management, training & development and talent management.",
        },
        {
          id: 2,
          name: "Sr. UI Developer",
          details:
            " UI developer's role is to translate creative software design concepts and ideas into reality using front end technology. ... The task of a user experience designer is to design and create a software interfaces by prioritizing Users and business requirements over technology limitations and constraints.",
        },
        {
          id: 3,
          name: "Accountant",
          details:
            "Accountants are responsible for a wide variety of finance-related tasks that are primarily associated with preparing financial records. These tasks oftentimes include computing taxes and preparing tax returns, organizing and maintaining financial records, and ensuring statements are accurate.",
        },
      ],
    };
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

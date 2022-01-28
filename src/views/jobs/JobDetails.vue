<template>
  <h1>Job Details Page</h1>
  <p>This has the id of {{ id }}</p>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      //id: this.$route.params.id,
    };
  },
};
</script>

<style></style>

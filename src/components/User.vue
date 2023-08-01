<template>
  <div>
    <p>{{ user.userName }}</p>
    <p>{{ user.lastName }}</p>
    <p>{{ user.email }}</p>
  </div>
</template>

<script>
export default {
  name: "User",
  props: {
    user: Object,
  },
  data() {
    return {};
  },
};
</script>

<style scoped></style>

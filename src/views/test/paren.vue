<template>
  <Model>
    <template v-slot:header>
      <p>Login</p>
    </template>
    <template>
      <label>Email</label>
      <input type="email" required />
      <label>Password</label>
      <input type="password" required />
      <input type="checkbox" />
      <span>Remember me</span>
    </template>
    <template v-slot:footer>
      <button>Cancel</button>
    </template>
  </Model>
</template>
<script>
import children from "@/views/test/testComponent/children.vue";
export default {
  components: {
    children,
  },
};
</script>

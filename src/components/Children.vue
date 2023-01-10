<template>
  <div class="children">
    <h2>This is children component</h2>
    <slot
      ><p>Đây là nội dung trong slot</p>
      <p>{{ test1 }}</p></slot
    >
  </div>
</template>
<script>
export default {
  name: "child",
  props: {
    test1: String,
  },
  data() {},
};
</script>
<style scoped></style>

<template>
  <div class="children">
    <div class="model">
      <div class="w-64 border shadow-md rounded">
        <div class="border-b p-2">
          <slot name="header" />
        </div>
        <div class="px-2 py-4">
          <slot />
        </div>
        <div class="border-t p-2 flex justify-end">
          <slot name="footer" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Children",
  props: {
    test1: String,
  },
};
</script>

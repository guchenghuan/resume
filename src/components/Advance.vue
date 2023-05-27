<template>
  <ul>
    <li v-for="(item, index) in advance" :key="index" style="font-size: 14px">
      {{ item }}
    </li>
  </ul>
</template>

<script>
export default {
  name: "Advance",
  props: {
    advance: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped lang="scss"></style>

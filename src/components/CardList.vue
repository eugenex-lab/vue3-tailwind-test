<template>
  <div class="border border-gray-300 p-4 rounded-md shadow-md">
    <h3 class="text-lg font-semibold">{{ user.name }}</h3>
    <p class="text-gray-600">{{ user.phoneNUmber }}</p>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    user: Object,
  },
};
</script>

<style scoped>
/* Add your component-specific styles here */
</style>
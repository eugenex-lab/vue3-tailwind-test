<template>
  <div class="total-expenses rounded-lg p-4 flex items-center justify-between bg-gradient-to-r from-purple-500 via-pink-500 to-red-500">
    <div class="flex flex-col">
      <div class="text-2xl font-bold text-white">{{ formattedTotal }} NGN</div>
      <div class="text-sm text-white">{{ label }}</div>
    </div>
    <img src="https://i.ibb.co/XySKnfq/ionicon-person.png" alt="Person Icon" class="ml-4" />
  </div>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: '',
    },
    total: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    formattedTotal() {
      return this.total.toLocaleString();
    },
  },
};
</script>

<style scoped>
.total-expenses {
  border: 2px solid #e2e8f0;
  background-color: #f7fafc;
}
</style>

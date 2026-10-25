<template>
  <div class="calendar">
    <input
      v-model="selectedDate"
      type="date"
      @change="emitDate"
    >
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedDate: ''
    };
  },
  methods: {
    emitDate() {
      this.$emit('date-selected', this.selectedDate);
    }
  }
};
</script>

<style scoped>
.calendar {
  margin: 20px 0;
}
</style>
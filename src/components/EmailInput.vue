<template>
  <div>
    <input
      v-model="email"
      type="email"
      placeholder="Enter your email"
      @input="validateEmail"
    >
    <span v-if="!isValidEmail && email">Invalid email format</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      isValidEmail: true,
    };
  },
  methods: {
    validateEmail() {
      const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      this.isValidEmail = emailPattern.test(this.email);
      this.$emit('email-entered', this.isValidEmail ? this.email : '');
    },
  },
};
</script>

<style scoped>
input {
  margin: 10px 0;
  padding: 8px;
  width: 100%;
}

span {
  color: red;
  font-size: 12px;
}
</style>
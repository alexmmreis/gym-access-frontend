<template>
  <div class="home">
    <h1>Select a Date and Enter Your Email</h1>
    <Calendar @date-selected="updateDate" />
    <EmailInput @email-entered="updateEmail" />
    <button
      :disabled="!isFormValid"
      @click="pay"
    >
      Pay
    </button>
  </div>
</template>

<script>
import Calendar from '../components/Calendar.vue';
import EmailInput from '../components/EmailInput.vue';

export default {
  components: {
    Calendar,
    EmailInput
  },
  data() {
    return {
      selectedDate: null,
      enteredEmail: ''
    };
  },
  computed: {
    isFormValid() {
      return this.selectedDate && this.enteredEmail;
    }
  },
  methods: {
    updateDate(date) {
      this.selectedDate = date;
    },
    updateEmail(email) {
      this.enteredEmail = email;
    },
    pay() {
      // Logic for payment processing
      alert(`Paying for ${this.enteredEmail} on ${this.selectedDate}`);
    }
  }
};
</script>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
}
button {
  margin-top: 20px;
}
</style>
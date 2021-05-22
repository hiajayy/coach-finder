<template>
  <section>
    <base-card>
      <h2>Register as a coach now!</h2>
      <coach-form @save-data="saveData"></coach-form
    ></base-card>
  </section>
</template>

<script>
import CoachForm from '../../components/coaches/CoachForm.vue';
export default {
  components: {
    CoachForm
  },

  methods: {
    saveData(data) {
      // calling coaches action
      this.$store.dispatch('coaches/registerCoach', data);

      //forward/redirect with back enable
      // this.$router.push('/coaches');

      //redirect and go back disable(not stored in history)
      this.$router.replace('/coaches');
    }
  }
};
</script>

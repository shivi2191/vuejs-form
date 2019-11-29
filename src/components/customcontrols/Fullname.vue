<template>
  <div>
    <div class="form-group">
      <label for="idFirstName">First Name</label>
      <input
        type="text"
        name="First Name"
        class="form-control"
        :value="firstName"
        id="idFirstName"
        @change="onNameChange(true, $event)"
      />
    </div>
    <div class="form-group">
      <label for="idLastName">Last Name</label>
      <input
        type="text"
        name="Last Name"
        id="idLastName"
        :value="lastName"
        class="form-control"
        @change="onNameChange(false, $event)"
      />
    </div>
  </div>
</template>
<script>
export default {
  props: ["value"],
  computed: {
    firstName() {
      if (this.value !== undefined) {
        return this.value.split(" ")[0];
      }
    },
    lastName() {
      if (this.value !== undefined) {
        return this.value.split(" ")[1];
      }
    }
  },
  methods: {
    onNameChange(isFirst, name) {
      var name,
          lastname,
          firstname;
      if (isFirst) {
        lastname = this.lastName !== undefined ? this.lastName : "";
        name = event.target.value + " " + lastname;
      } else {
        firstname = this.firstName !== undefined ? this.firstName : "";
        name =  firstname + " " + event.target.value;
      }

      this.$emit("completeName", name);
    }
  }
};
</script>
<style scoped>
</style>
<template>
  <div>
    <div class="form-group">
      <label for="idFirstName">First Name</label>
      <input
        type="text"
        name="First Name"
        class="form-control"
        v-model.lazy="UserDetails.firstName"
        id="idFirstName"
      />
    </div>
    <div class="form-group">
      <label for="idLastName">Last Name</label>
      <input
        type="text"
        name="Last Name"
        id="idLastName"
        v-model.lazy="UserDetails.lastName"
        class="form-control"
      />
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
</style>
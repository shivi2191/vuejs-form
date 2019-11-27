<template>
  <div class="container">
    <form>
      <fieldset>
        <legend>Personal information:</legend>
        <div class="row">
          <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
            <h1>Fill your details</h1>
            <hr />
            <div class="form-group">
              <label for="idFirstName">First Name</label>
              <input type="text" name="First Name" class="form-control" id="idFirstName" />
            </div>
            <div class="form-group">
              <label for="idLastName">Last Name</label>
              <input type="text" name="Last Name" id="idLastName" class="form-control" />
            </div>
            <div class="form-group">
              <label for="idEmail">Email</label>
              <input type="email" name="Email" id="idEmail" class="form-control" />
            </div>
            <div class="form-group">
              <label for="idPassword1">Password</label>
              <input type="password" name="Password" id="idPassword1" class="form-control" />
            </div>
            <div class="form-group">
              <label for="idPassword2">Confirm Password</label>
              <input type="password" name="Password" id="idPassword2" class="form-control" />
            </div>
            <div class="form-group">
                <SwitchBtn></SwitchBtn>
            </div>
          </div>
        </div>
      </fieldset>
    </form>
  </div>
</template>

<script>
import SwitchBtn from "./customcontrols/Switch.vue"
export default {
    components: {
        SwitchBtn: SwitchBtn
    }
}
</script>

<style scoped>
@import url("https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css");
</style>
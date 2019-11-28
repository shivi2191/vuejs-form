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
              <input type="text" name="First Name" class="form-control" v-model.lazy="UserDetails.firstName" id="idFirstName" />
            </div>
            <div class="form-group">
              <label for="idLastName">Last Name</label>
              <input type="text" name="Last Name" id="idLastName" v-model.lazy="UserDetails.lastName" class="form-control" />
            </div>
            <div class="form-group">
              <label for="idEmail">Email</label>
              <input type="email" name="Email" id="idEmail" v-model.lazy="UserDetails.email" class="form-control" />
            </div>
            <div class="form-group">
              <label for="idPassword1">Password</label>
              <input type="password" name="Password" id="idPassword1" v-model.lazy="UserDetails.password" class="form-control" />
            </div>
            <div class="form-group">
              <label for="idPassword2">Confirm Password</label>
              <input type="password" name="Password" id="idPassword2" v-model.lazy="UserDetails.confirmPassword" class="form-control" />
            </div>
            <div class="form-group" v-if="displaySwitch === true">
              <label for="idPassword2">Save Data</label>
              <SwitchBtn @switchStatus="checkSwitchState"></SwitchBtn>
            </div>
            <div class="form-group">
              <button class="btn btn-default" @click.prevent="onSubmitClick">Submit</button>              
            </div>
          </div>
        </div>
      </fieldset>
    </form>
  </div>
</template>

<script>
import SwitchBtn from "./customcontrols/Switch.vue";
export default {
  data() {
    return {
      UserDetails: {
        firstName: "",
        lastName: "",
        email: "",
        password: "",
        confirmPassword: "",
        switchState: ""
      },
      displaySwitch: true,
      saveData: false,
      submitClicked : false
    };
  },
  components: {
    SwitchBtn: SwitchBtn
  },
  methods: {
    onSubmitClick(){
      this.submitClicked = true;
      this.$emit('submit-clicked', this.submitClicked);
      this.$emit('form-data', this.UserDetails);
      this.displaySwitch = false;
    },

    checkSwitchState(bSwitchState){
      if(bSwitchState){
        this.UserDetails.switchState = 'Yes'
      }else{
        this.UserDetails.switchState = 'No'
      };
    }
  }
};
</script>

<style scoped>
@import url("https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css");
</style>
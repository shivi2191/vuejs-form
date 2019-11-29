<template>
  <div class="container">
    <form>
      <fieldset>
        <legend>Personal information:</legend>
        <div class="row">
          <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
            <h1>Fill your details</h1>
            <hr />
            <FullName v-model="UserDetails.fullname" @completeName="getCompleteName"></FullName>
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
import FullName from "./customcontrols/Fullname.vue";
export default {
  data() {
    return {
      UserDetails: {
        fullname: "",
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
    SwitchBtn: SwitchBtn,
    FullName: FullName
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
    },
    getCompleteName(value){
      this.UserDetails.fullname = value;
    }
  }
};
</script>

<style scoped>
@import url("https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css");
</style>
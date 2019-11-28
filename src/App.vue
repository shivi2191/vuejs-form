<template>
    <div class="container">
        <Details @submit-clicked="detectSubmit" @form-data="sendDataToCollection"></Details>
        <hr>
        <CollectedDetails :formdetails='formData' v-if="submitStatus===true"></CollectedDetails>
    </div>
</template>

<script>
    import Details from './components/Form.vue'
    import CollectedDetails from './components/CollectedDetails.vue'
    export default {
        components: {
            Details: Details,
            CollectedDetails: CollectedDetails
        },
        data(){
            return {
                submitStatus: false,
                formData: {}
            }
        },
        methods: {
            detectSubmit(bValue){
               this.submitStatus = bValue;
            },

            sendDataToCollection(obj){
                this.formData = obj;
            }
        }
    }
</script>

<style>
@import url("https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css");
</style>

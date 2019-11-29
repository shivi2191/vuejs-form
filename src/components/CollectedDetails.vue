<template>
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4><b>Your Data</b></h4>
                    </div>
                    <div class="panel-body">
                        <p><b>Name:</b> {{formdetails.fullname}}</p>
                        <p><b>Mail:</b>  {{formdetails.email}}</p>
                        <p><b>Password:</b> {{formdetails.password}} </p>
                        <p><b>Store in Database:</b> <b>{{formdetails.switchState}}</b></p>
                    </div>
                </div>
            </div>
        </div>
</template>
<script>
export default {
    props:['formdetails']
}
</script>

<style scoped>

</style>
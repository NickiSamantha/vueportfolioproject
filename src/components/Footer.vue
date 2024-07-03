<template>
    
    <div class="container-fluid background">
        <!-- /*take the entire width of a page*/ -->

<div class="row sticky-bottom pt-3">
    <p class="lead">Nicki's Portfolio &copy; 
        <span> {{ cYear }}</span>
    </p>
</div>
    </div>
</template>

<script>
    export default {
        name: "FooterComp",
        data () {
            return{
                cYear: new Date ().
                getUTCFullYear()
            }
        },

    }
</script>

<style scoped>
.background{
    background: linear-gradient( #fce6d3, #fad9d5, #fbb7c7);
}
</style>
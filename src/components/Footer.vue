<template>
    
    <div class="container-fluid">
        <!-- /*take the entire width of a page*/ -->

<div class="row sticky-bottom">
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

<style lang="scss" scoped>

</style>
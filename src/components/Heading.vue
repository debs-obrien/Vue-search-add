<template>
        <div class="page-header cf">
            <h2>{{title}}</h2>
            <!-- dynamically insert search form here (optional) -->

        </div>

</template>

<script>
    export default {
        name: 'Heading',
        props: {
            title: String,
        },
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

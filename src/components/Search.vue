<template>
    <div class="search">
        <label>search</label>
        <input type="text" placeholder="Search for someone.." >
    </div>

</template>

<script>
    export default {
        name: 'Search',
        props: {
            search: ''
        },
        updateFilter() {
            console.log('update filter');
            bus.$emit('filter', this.myinput);
        },
    data() {
        return {
            myinput: undefined,
        };
    },
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

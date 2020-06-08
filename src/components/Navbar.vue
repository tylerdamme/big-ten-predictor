<template>
    <div>
    <b-navbar toggleable="sm" type="dark" variant="dark">
        <b-navbar-toggle target="nav-text-collapse"></b-navbar-toggle>

        <b-navbar-brand>Big Ten Predictor</b-navbar-brand>

        <b-collapse id="nav-text-collapse" is-nav>
        <b-navbar-nav>
            <b-nav-text>{{ timestamp }} Season</b-nav-text>
        </b-navbar-nav>
        </b-collapse>
    </b-navbar>
    </div>
</template>

<script>
export default {

    data() {
        return {
            timestamp: ""
        };
    },

    created() {
        this.getYear();
    },

    methods: {
        getYear: function() {
            const today = new Date();
            let currentYear = today.getFullYear();
            this.timestamp = currentYear;
        }
    }
}
</script>

<style>

</style>
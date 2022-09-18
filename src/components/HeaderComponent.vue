<template>
    <nav class="navbar navbar-expand-lg navbar-dark">
        <a class="navbar-brand" href="/">ACXDev</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
                <MainNavItemComponent v-for="url in urls" v-bind:key="url.id" :url="url" />
            </ul>
        </div>
    </nav>
</template>

<script>
    import axios from 'axios';
    import MainNavItemComponent from './Navigation/MainNavItemComponent.vue';
    
    export default {
        name: 'HeaderComponent',
        components: {
            MainNavItemComponent
        },
        data() {
            return {
                urls: null,
            }
        },
        created: function() {
            axios.get('http://localhost:8000/api/menu')
                .then(res=> {
                    this.urls = res.data
                })
        }
    }
</script>

<style>

</style>
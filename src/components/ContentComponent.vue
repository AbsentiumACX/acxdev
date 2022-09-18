<template>
    <div class="row">
        <div class="jumbotron bg-dark col-md-12">
            <h1>{{content.title}}</h1>
        </div>
        <div class="col-md-3"></div>
        <div class="col-md-6 text-left" v-html="content.content"></div>
        <div class="col-md-3"></div>
    </div>
</template>

<script>
    export default {
        name: 'ContentComponent',
        props: ['content'],
    }
</script>

<style>
    .jumbotron {
        background-image: url('~@/assets/jumbotron.jpg');
        background-size: cover;
        box-shadow:inset 0 0 0 200px rgba(0, 0, 0, 0.75);
    }
</style>
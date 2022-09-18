<template>
    <li v-if="!url.children.length" class="nav-item">
        <a class="nav-link" :href="url.title">{{url.title}}</a>
    </li>
    <li v-else class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" :href="url.title" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        {{url.title}}
        </a>
        <div class="dropdown-menu bg-dark" aria-labelledby="navbarDropdown">
            <ChildNavItemComponent v-for="child in url.children" v-bind:key="child.id" :child="child" />
        </div>
    </li>
</template>

<script>
    import ChildNavItemComponent from './ChildNavItemComponent.vue'

    export default {
        name: 'MainNavItemComponent',
        props: ['url'],
        components: {
            ChildNavItemComponent
        }
    }
</script>

<style>
    
</style>
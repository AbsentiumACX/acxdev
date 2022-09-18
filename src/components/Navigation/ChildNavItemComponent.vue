<template>
    <a class="dropdown-item text-light" :href="child.title">
        {{child.title}}
    </a>
</template>

<script>
    export default {
        name: 'ChildNavItemComponent',
        props: ['child']
    }
</script>

<style>
    .dropdown-item:hover {
        background-color: #212529;
    }
</style>
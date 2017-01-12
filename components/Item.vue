<style>

</style>

<template>
    <li>
        <a href="javascript:void(0)">{{name}}</a>
    </li>
</template>

<script>
    import Item from './Item.vue'
    export default {
        props: ['name'],
        data() {
            return {
            }
        }
    }
</script>
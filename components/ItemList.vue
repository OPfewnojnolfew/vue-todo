<style>

</style>

<template>
    <div>
        <p class="map-resultcontainer-head">
            共搜索到 <i>{{ count }}</i> 条结果
            <a href="javascript:void(0)"></a>
        </p>
        <ul>
            <item v-for="dataitem in dataitems" :name="dataitem.name"></item>
        </ul>
    </div>

</template>

<script>
    import Item from './Item.vue'
    export default {
        props: ['count', 'dataitems'],
        components: {
            Item
        },
        data() {
            return {

            }
        }
    }
</script>
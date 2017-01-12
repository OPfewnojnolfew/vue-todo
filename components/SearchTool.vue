<template>
    <div>
        <search-box @search="search" @clear="clear"></search-box>
        <item-list :dataitems="dataitems" :count="count"></item-list>
    </div>
</template>

<script>
    import SearchBox from './SearchBox.vue'
    import ItemList from './ItemList.vue'
    export default {
        data() {
            return {
                count: 0,
                dataitems: []
            }
        },
        components: {
            SearchBox, ItemList
        },
        methods: {
            search: function (keyword) {
                var self = this;
                $.get('/service/traffic/roadMonitor/search', {
                    keyword: keyword,
                    from: 'pva'
                }).then(function (res) {
                    var c = 0, l = [];
                    if (res && res.code == 200 && res.data) {
                        c = res.data.length;
                        l = res.data;
                    }
                    self.count = c;
                    self.dataitems = l;
                });
            },
            clear: function () {
                this.count = 0;
                this.dataitems = [];
            }
        }
    }
</script>
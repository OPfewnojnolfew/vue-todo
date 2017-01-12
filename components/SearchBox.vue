<template>
    <div class="search-tool">
        <i class="border-tr"></i>
        <i class="border-br"></i>
        <i class="border-bl"></i>
        <i class="border-tl"></i>
        <form onsubmit="return false">
<input type="text" placeholder="请输入道路名称或设备名称..." v-model="name" />
<a href="javascript:void(0)" title="清空" @click="clear()">X</a>
<button type="submit" title="搜索" @click="search()">S</button>
</form>
</div>
</template>

<script>
    export default {
        data() {
            return {
                name: ''
            }
        },
        methods: {
            clear: function () {
                if (!this.name) {
                    return;
                }
                this.$emit('clear', this.name = '');
            },
            search: function () {
                if (!this.name) {
                    return;
                }
                this.$emit('search', this.name);
            }
        }
    }
</script>
<style>
.search-tool{
    position: relative;
    border: 1px solid #69789e;  
}
.search-tool input[type=text] {
    border: none;
    border-right: 0;
    padding: 0 25px 0 15px;
    width: 353px;
    background: rgba(21, 31, 78, .6);
    color: #7895bc;
    height: 35px;
}
</style>
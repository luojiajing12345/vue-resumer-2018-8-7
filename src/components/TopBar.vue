<template>
    <div id='topbar'>
        <div class='logo'>
            VueResumer
        </div>
        <div class="actions">
            <el-button type="primary">注册</el-button>
            <el-button type="info">登陆</el-button>
            <el-button v-on:click="preview">预览</el-button>
        </div>
    </div>
</template>
<style lang='scss'>
#topbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
    font-size: 20px;
}
</style>

<script>
    export default{
        methods:{
            preview(){
                this.$emit('preview')
            }
        }
    }
</script>
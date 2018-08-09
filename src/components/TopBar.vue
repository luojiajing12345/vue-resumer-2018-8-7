<template>
    <div id='topbar'>
        <div class='logo'>
            VueResumer
        </div>
        <div class="actions">
            <button>注册</button>
            <button>登陆</button>
            <el-button>默认按钮</el-button>
            <el-button type="primary">主要按钮</el-button>
            <el-button type="success">成功按钮</el-button>
            <el-button type="info">信息按钮</el-button>
            <el-button type="warning">警告按钮</el-button>
            <el-button type="danger">危险按钮</el-button>
        </div>
    </div>
</template>
<style lang='scss'>
    #topbar{
        display: flex;
        justify-content: space-between;
        padding: 20px
    }

</style>
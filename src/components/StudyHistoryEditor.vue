<template>
    <div>
        <h2>学习经历</h2>
        <el-form class="container">
            <div class='works' v-for="(item,index) in items">
                <el-form-item label="学校">
                    <el-input v-model="item.school"></el-input>
                </el-form-item>
                <el-form-item label="时间">
                    <el-input v-model="item.duration"></el-input>
                </el-form-item>
                <el-form-item label="学位">
                    <el-input v-model="item.degree"></el-input>
                </el-form-item>
                <el-button class="rmButton" type="primary" v-on:click='removeItem(index)'>删除</el-button>
                <hr>
            </div>
            <el-button type="primary" v-on:click='addItem'>添加</el-button>
        </el-form>
    </div>
</template>

<script>
export default {
    props: ["items"],
    methods: {
        addItem() {
            this.items.push({
                school: "",
                durantion: "",
                degree:''
            });
        },
        removeItem(index) {
            this.items.splice(index, 1);
        }
    }
};
</script>
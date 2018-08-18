<template>
    <div>
        <h2>{{title}}</h2>
        <el-form class="container">
            <div class='works' v-for="(work,index) in items" v-bind:key="index">
                <el-form-item v-for="key in keys" v-bind:label="labels[key] || key" v-bind:key="key">
                    <el-input v-model="work[key]"></el-input>
                </el-form-item>
                <el-button class="rmButton" type="primary" v-on:click='removeWorkHistory(index)'>删除</el-button>
                <hr>
            </div>
            <el-button type="primary" v-on:click='addWorkHistory'>添加</el-button>
        </el-form>
    </div>
</template>


<script>
export default {
    props: ["items", "labels","title"],
    computed: {
        keys() {
            return Object.keys(this.items[0]);
        }
    },
    methods: {
        addWorkHistory() {
            const empty = {};
            this.keys.map(key => {
                empty[key] = "";
            });
            this.items.push(empty || key);
        },
        removeWorkHistory(index) {
            if (index > 0) {
                this.items.splice(index, 1);
            } else {
                alert("无法删除");
            }
        }
    }
};
</script>

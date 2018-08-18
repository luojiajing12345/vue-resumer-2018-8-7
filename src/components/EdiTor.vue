<template>
    <div id='editor'>
        <nav>
            <ol>
                <li v-for="i in [0,1,2,3,4,5]" v-bind:class='{active: currentTab === i}' v-on:click='currentTab = i'>
                    <svg class="icon" aria-hidden="true">
                        <use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
                    </svg>
                </li>
            </ol>
        </nav>
        <ol class="panes">
            <li v-bind:class="{active:currentTab === 0}">
                <h2>个人信息</h2>
                <el-form>
                    <el-form-item label="名称">
                        <el-input v-model="profile.name"></el-input>
                    </el-form-item>
                    <el-form-item label="城市">
                        <el-input v-model="profile.city"></el-input>
                    </el-form-item>
                    <el-form-item label="出生年月">
                        <el-input v-model="profile.bitrh"></el-input>
                    </el-form-item>
                </el-form>
            </li>
            <li v-bind:class="{active:currentTab === 1}">
                <h2>工作经历</h2>
                <el-form class="container">
                    <div class='works' v-for="(work,index) in workHistory">
                        <el-form-item label="公司">
                            <el-input v-model="work.company"></el-input>
                        </el-form-item>
                        <el-form-item label="项目">
                            <el-input v-model="work.content"></el-input>
                        </el-form-item>
                        <el-button class="rmButton" type="primary" v-on:click='removeWorkHistory(index)'>删除</el-button>
                        <hr>
                    </div>
                    <el-button type="primary" v-on:click='addWorkHistory'>添加</el-button>

                </el-form>
            </li>
            <li v-bind:class="{active:currentTab === 2}">
                <h2>学习经历</h2>
            </li>
            <li v-bind:class="{active:currentTab === 3}">
                <h2>项目经历</h2>
            </li>
            <li v-bind:class="{active:currentTab === 4}">
                <h2>获奖情况</h2>
            </li>
            <li v-bind:class="{active:currentTab === 5}">
                <h2>联系方式</h2>
            </li>
        </ol>
    </div>
</template>

<script>
export default {
    data() {
        return {
            currentTab: 0,
            icons: [
                "credentials_icon",
                "book",
                "work0",
                "aixin1",
                "jiangbei",
                "dianhua"
            ],
            profile: {
                name: "",
                city: "",
                bitrh: ""
            },
            workHistory: [{ company: "", content: "" }]
        };
    },
    methods: {
        addWorkHistory() {
            this.workHistory.push({
                company: "",
                content: ""
            });
        },
        removeWorkHistory(index) {
            this.workHistory.splice(index, 1);
        }
    }
};
</script>


<style lang='scss'>
#editor {
    min-height: 100px;
    display: flex;
    > nav {
        background: black;
        > ol {
            width: 80px;
            > li {
                padding: 15px 0;
                text-align: center;
                &.active {
                    background: white;
                    > .icon {
                        fill: black;
                    }
                }
            }
        }
    }
    > .panes {
        flex: 1;
        .container {
            position: relative;
            .works{
                padding-bottom: 20px;
            }
            .rmButton {
                position: absolute;
                right: 0;
            }
        }
        > li {
            display: none;
            padding: 40px;
            height: 100%;
            overflow: auto;
            &.active {
                display: block;
            }
        }
    }
}
.icon {
    width: 40px;
    height: 30px;
    fill: white;
}
</style>

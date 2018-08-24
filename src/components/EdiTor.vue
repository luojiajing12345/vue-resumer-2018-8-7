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
                <ProfileEditor v-bind:profile="resume.profile" />
            </li>
            <li v-bind:class="{active:currentTab === 1}">
                <ArrayEditor v-bind:items="resume.workHistory" v-bind:labels="{company: '公司',content:'工作内容'}" v-bind:title="'工作经历'" />
            </li>
            <li v-bind:class="{active:currentTab === 2}">
                <ArrayEditor v-bind:items="resume.studyHistory" v-bind:labels="{school: '学校',duration:'时间',degree:'学位'}" v-bind:title="'学习经历'" />
            </li>
            <li v-bind:class="{active:currentTab === 3}">
                <ArrayEditor v-bind:items="resume.projects" v-bind:labels="{name: '项目名称',content:'工作内容'}" title="项目经历" />
            </li>
            <li v-bind:class="{active:currentTab === 4}">
                <ArrayEditor v-bind:items="resume.awards" v-bind:labels="{name: '奖励详情'}" title="获奖情况" />
            </li>
            <li v-bind:class="{active:currentTab === 5}">
                <h2>联系方式</h2>
                <h2>个人信息</h2>
                <el-form>
                    <el-form-item label="QQ">
                        <el-input v-model="resume.contacts.qq"></el-input>
                    </el-form-item>
                    <el-form-item label="微信">
                        <el-input v-model="resume.contacts.wx"></el-input>
                    </el-form-item>
                    <el-form-item label="邮箱">
                        <el-input v-model="resume.contacts.email"></el-input>
                    </el-form-item>
                    <el-form-item label="手机">
                        <el-input v-model="resume.contacts.phone"></el-input>
                    </el-form-item>
                </el-form>
            </li>
        </ol>
    </div>
</template>

<script>
import ProfileEditor from "./ProfileEditor";
import ArrayEditor from "./ArrayEditor";
export default {
    components: { ProfileEditor, ArrayEditor },
    props:['resume'],
    data() {
        return {
            currentTab: 0,
            icons: [
                "credentials_icon",
                "work0",
                "book",
                "aixin1",
                "jiangbei",
                "dianhua"
            ],

        };
    },
    methods: {}
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
            .works {
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

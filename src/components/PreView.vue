<template>
    <div id='preview'>
        <h1>{{resume.profile.name || '请填写姓名'}}</h1>
        <p>{{resume.profile.city || '请填写城市'}} | {{resume.profile.bitrh || '请填写出生年月'}}</p>
        <hr>
        <section v-if="filter(resume.workHistory).length>0">
            <h2>工作经历</h2>
            <ul>
                <li v-for="work in filter(resume.workHistory)">
                    {{work.company}} {{work.content}}
                </li>
            </ul>
        </section>
        <section v-if="filter(resume.studyHistory).length>0">
            <h2>学习经历</h2>
            <ul>
                <li v-for="study in filter(resume.studyHistory)">
                    {{study.school}} {{study.duration}} {{study.degree}}
                </li>
            </ul>
        </section>
    </div>
</template>

<style>
#preview {
}
</style>

<script>
export default {
    props: ["resume"],
    methods: {
        filter(array) {
            return array.filter(item => !this.isEmpty(item));
        },
        isEmpty(object) {
            let empty = true;
            for (let key in object) {
                if (object[key]) {
                    empty = false;
                    break;
                }
            }
            return empty;
        }
    }
};
</script>
<template>
  <div id="app" v-bind:class="{previewMode:previewMode}">
    <TopBar class='topbar' v-on:preview="preview"/>
    <main>    
    <EdiTor v-bind:resume="resume" class='editor'/>
    <PreView v-bind:resume="resume" class='preview'/>

    </main>
    <el-button id='exitPreview' v-on:click="exitPreview" >退出预览</el-button>
  </div>
</template>

<script>
//import frank from './components/frank'
import TopBar from "./components/TopBar";
import PreView from "./components/PreView";
import EdiTor from "./components/EdiTor";
export default {
  data() {
    return {
      previewMode:false,
      resume:{
            profile: {name: "",city: "",bitrh: ""},
            workHistory: [{ company: "", content: "" }],
            studyHistory: [{ school: "", duration: "", degree: "" }],
            projects: [{ name: "", content: "" }],
            awards: [{ name: "" }],
            contacts:[{qq:'',wx:'',emain:'',phone:''}]
      }
    }
  },
  methods:{
    exitPreview(){
      this.previewMode = false
    },
    preview(){
      this.previewMode =true
    }
  },
  components: {
    TopBar,
    PreView,
    EdiTor
  },

};
</script>

<style lang='scss'>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;
  display: flex;
  flex-direction: column;
}
.topbar {
  box-shadow: 0 0 3px hsla(0, 0, 0, 0.5);
  position: relative;
  z-index: 1;
}
.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  overflow: hidden;

}
main {
  display: flex;
  flex: 1;
  background: #ddd;
  > .editor {
    width: 40em;
    margin: 20px 10px 20px 10px;
    background: white;
    box-shadow: 0 0 3px hsla(0, 0, 0, 0.5);
    border-radius: 10px;
    overflow:hidden;
  }
  > .preview {
    flex: 1;
    margin: 20px 20px 20px 10px;
    background: white;
    box-shadow: 0 0 3px hsla(0, 0, 0, 0.5);
    border-radius: 10px;
  }
}
.previewMode>#topbar{
  display: none
}
.previewMode #editor{
  display: none
}
.previewMode #preview{
  max-width: 800px;
  margin: 40px auto;
}
#exitPreview {
  display: none
}
.previewMode #exitPreview{
  display: inline-block;
  position: fixed;
  right: 16px;
  bottom:16px;
} 
</style>

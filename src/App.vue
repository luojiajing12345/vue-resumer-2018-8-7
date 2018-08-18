<template>
  <div id="app">
    <TopBar class='topbar'/>
    <main>    
    <EdiTor class='editor'/>
    <PreView class='preview'/>

    </main>
  </div>
</template>

<script>
//import frank from './components/frank'
import TopBar from "./components/TopBar";
import PreView from "./components/PreView";
import EdiTor from "./components/EdiTor";
export default {
  components: {
    TopBar,
    PreView,
    EdiTor
  }
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
    overflow:auto;
  }
  > .preview {
    flex: 1;
    margin: 20px 20px 20px 10px;
    background: white;
    box-shadow: 0 0 3px hsla(0, 0, 0, 0.5);
    border-radius: 10px;
  }
}
</style>

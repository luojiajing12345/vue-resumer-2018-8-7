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
import TopBar from './components/TopBar'
import PreView from './components/PreView'
import EdiTor from './components/EdiTor'
export default {
  components: {
    TopBar,PreView,EdiTor
  }
}
</script>

<style lang='scss'>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height:100vh;
  display:flex;
  flex-direction:column;
}
.topbar{
}
main{
  display:flex;
  flex:1;
  > .editor{
  width:20em;
  }
  > .preview{
  flex:1;
  }
}

</style>

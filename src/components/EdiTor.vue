<template>
    <div id='editor'>
        <nav>
            <ol>
                <li v-for = "i in [0,1,2,3,4,5]" 
                    v-bind:class = '{active: currentTab === i}' 
                    v-on:click = 'currentTab = i'
                    >
                    <svg class="icon" aria-hidden="true">
                        <use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
                    </svg>
                </li>
            </ol>
        </nav>
        <ol class="panes">
            <li v-bind:class="{active:currentTab === 0}">tab1</li>
            <li v-bind:class="{active:currentTab === 1}">tab2</li>
            <li v-bind:class="{active:currentTab === 2}">tab3</li>
            <li v-bind:class="{active:currentTab === 3}">tab4</li>
            <li v-bind:class="{active:currentTab === 4}">tab5</li>
            <li v-bind:class="{active:currentTab === 5}">tab6</li>
        </ol>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                currentTab:0,
                icons:['credentials_icon','book','work0','aixin1','jiangbei','dianhua']
            }
        }
    }
</script>


<style lang='scss'>

    #editor {
        min-height: 100px;
        display:flex;
        > nav{
            background: black;
            > ol{
                width:80px;
                > li{
                    padding:15px 0;
                    text-align:center;
                    &.active{
                        background:white;
                        > .icon{
                            fill:black;
                        }   
                    }
                }
            }
        }
        > .panes{
            >li{
              display: none;  
              &.active{
                  display: block;
              }
            }
        }
    }
    .icon{
         width: 40px;
         height: 30px;
         fill:white;
    }

</style>
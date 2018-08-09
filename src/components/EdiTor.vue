<template>
    <div id='editor'>
        <nav>
            <ol>
                <li>
                    <svg class="icon" aria-hidden="true">
                        <use xlink:href="#icon-shenfen"></use>
                    </svg>
                </li>
                <li>
                    <svg class="icon" aria-hidden="true">
                        <use xlink:href="#icon-book"></use>
                    </svg>
                </li>
                <li>
                    <svg class="icon" aria-hidden="true">
                        <use xlink:href="#icon-work0"></use>
                    </svg>
                </li>
                <li>
                        <svg class="icon" aria-hidden="true">
                        <use xlink:href="#icon-aixin"></use>
                    </svg>
                </li>
                <li>
                    <svg class="icon" aria-hidden="true">
                        <use xlink:href="#icon-jiangbei"></use>
                    </svg>
                </li>
                <li>
                    <svg class="icon" aria-hidden="true">
                        <use xlink:href="#icon-dianhua"></use>
                    </svg>
                </li>
            </ol>
        </nav>
        <ol class="panes"></ol>
    </div>
</template>
<style>
nav{
    background: black;
}
#editor {
  min-height: 100px;
}
.icon{
     width: 30px;
     height: 30px;
     fill:white;
}
</style>
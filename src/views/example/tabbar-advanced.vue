<template>
    <div class="flex-column">
        <!--标题栏-->
        <bui-header
                title="选项卡示例"
                :leftItem="leftItem"
                @leftClick="back">
        </bui-header>

        <!--选项卡-->
        <bui-tabbar
                :tabItems="tabItems"
                :currentTab="currentTab"
                showSelectedLine="true"
                @load="onTabLoad"
                @itemClick="onTabItemClick">
        </bui-tabbar>

        <div style="flex: 1; background-color:grey">
            <bui-tabbar-item-a index="0" :currentTabIndex="currentTabIndex">
                <scroller>
                    <div style="height: 1500px;width: 750px">
                        <text>选项卡1</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                        <text>我是滚动的内容</text>
                    </div>
                </scroller>
            </bui-tabbar-item-a>

            <bui-tabbar-item-a index="1" :currentTabIndex="currentTabIndex">
                <text>选项卡2</text>
            </bui-tabbar-item-a>

            <bui-tabbar-item-a index="2" :currentTabIndex="currentTabIndex">
                <text>选项卡3</text>
            </bui-tabbar-item-a>

            <bui-tabbar-item-a index="3" :currentTabIndex="currentTabIndex">
                <text>选项卡4</text>
            </bui-tabbar-item-a>
        </div>
    </div>
</template>

<style lang="sass" src="bui-weex/src/css/buiweex.scss"></style>

<script>
    var buiweex = require("bui-weex");
    module.exports = {
        data: function () {
            return {
                leftItem: {
                    icons: 'icon-back',
                },
                //当前选择的tab
                currentTab: "tab1",
                currentTabIndex: "1",
                tabItems: [
                    {
                        tabId: "tab1",
                        title: "首页",
                        icon: "icon-home"
                    },
                    {
                        tabId: "tab2",
                        icon: "icon-liwu",
                        title: "动态"
                    },
                    {
                        tabId: "tab3",
                        icon: "icon-user",
                        title: "我的"
                    },
                    {
                        tabId: "tab4",
                        icon: "icon-video",
                        title: "直播"
                    }
                ],
                itemStyleEx: {},
                containerStyleEx: {},
            }
        },
        components: {
            "bui-tabbar": buiweex.buiTabbar,
            "bui-tabbar-item-a":buiweex.buiTabbarItemA
        },
        methods: {
            "back": function () {
                buiweex.pop();
            },
            //选项卡加载完成事件,必须实现
            "onTabLoad": function (tabId, index) {
                this.currentTab = tabId;
            },
            //选项卡点击事件,必须实现
            "onTabItemClick": function (e, tabId, index) {
                this.currentTab = tabId;
                this.index = index;
                this.currentTabIndex = index;
            }
        }
    }
</script>

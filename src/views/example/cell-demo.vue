<template>
    <div>
        <bui-header
                title="单元格（bui-cell）"
                :leftItem="leftItem"
                @leftClick="back">
        </bui-header>

        <scroller>
            <bui-cell title="文字内容" label="标题" desc="描述信息"></bui-cell>
            <bui-cell label="公司名称" >
                <input slot="title" class="input" placeholder="请输入公司名称" />
            </bui-cell>

            <bui-cell title="标题文字" @cellClick="cellClick"  :cellStyle="cellStyle">
               <bui-icon slot="action" name="ion-ios-arrow-right"></bui-icon>
            </bui-cell>

            <bui-cell title="标题文字" @cellClick="cellClick" :cellStyle="cellStyle">
                <bui-icon slot="label" style="margin-right: 10px" name="ion-ios-cloud-upload-outline"></bui-icon>
                <bui-icon slot="action" name="ion-ios-arrow-right"></bui-icon>
            </bui-cell>

            <bui-cell :cellStyle="cellStyle"  label="开发者选项">
                <switch checked="true"></switch>
            </bui-cell>

        </scroller>
    </div>
</template>

<style lang="scss" src="src/css/buiweex.scss"></style>

<style>
    .input {
        height: 40px;
        line-height: 40px;
    }
</style>

<script>
    export default {
        data: function () {
            return {
                leftItem: {
                    icon: 'ion-chevron-left'
                },
                cellStyle:{
                    "background-color:active":"#f2f2f2"
                }
            }
        },
        methods: {
            back() {
                this.$pop();
            },
            cellClick(){
                this.$toast("click");
            }
        }
    }
</script>
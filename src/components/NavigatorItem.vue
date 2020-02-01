<template>
    <div class="NavigatorItem">
        <div class="title" v-bind:id="categoryName">
            <a-icon type="tag"></a-icon><span>{{ categoryName }}</span>
        </div>

        <div class="station">
            <div class="wrap" v-for="(item, index) in stationArray" v-bind:key="index">
                <div class="item" v-on:click="jumpToTarget(index)">
                    <div>
                        <img v-bind:src="item.siteAlias" style="width: 40px; height: 40px; margin-left: 10px; margin-top: 20px">
                    </div>
                    <div class="desc">
                        <span>{{ item.siteName }}</span>
                        <p>{{ item.siteDesc }}</p>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>

<script lang="ts">
import {Vue, Component, Prop} from "vue-property-decorator";

@Component({
    name: "NavigatorItem",
    components : {

    }
})
export default class NavigatorItem extends Vue {

    @Prop(String)
    public categoryName !: string;  //分类名称


    @Prop(Array)
    public stationArray !: Array<Station>;   //站点列表


    private jumpToTarget(index: number){
        window.location.href = this.stationArray[index].siteUrl;
    }
}


class Station {

    siteName !: string;

    siteDesc !: string;

    siteUrl  !: string;

    siteAlias !: string;
}




</script>

<style scoped>
.title {
    color: #555555;
    display: flex;
    flex-direction: row;
    margin-left: 20px;
    padding-top: 30px;
}

.title span {
    font-size: 18px;
    margin-left: 10px;
}

.station {
    margin: 10px 20px;
    flex-direction: row;
    flex-wrap: wrap;
    display: flex;
}

.wrap {
    width: 25%;
}

.item {
    border: #E4ECF3 1px solid;
    display: flex;
    flex-direction: row;
    margin-right: 20px;
    height: 100px;
    margin-top: 20px;
}

.desc {
    margin: 10px 20px;
    display: flex;
    flex-direction: column;
}

.desc span {
    font-size: 18px;
    font-weight: bold;
}
</style>
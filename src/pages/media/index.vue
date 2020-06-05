<template>
    <view class="content">             
        <van-search class="input-box" :value="value" placeholder="请输入搜索关键词" />
        <van-grid class="book-grid" column-num="3" :border="false">
            <van-grid-item use-slot v-for="(item,index) in 3" :key="index">
                <image style="width:100%;height:90px;" :src=" 'https://img.yzcdn.cn/vant/apple-'+ (index + 1)+'.jpg'" />
            </van-grid-item>            
        </van-grid>   
        <van-tabs class="book-category" :active="0" @change="changeBookType">
            <van-tab v-for="(item,index) in tabs" :key="index" :title="item.title">
                <view>
                   <van-card num="2" price="2.00" :desc="item.desc" :title="item.productTitle" :thumb="item.thumb" />
                </view>
            </van-tab>
        </van-tabs>   
    </view>
</template>
<script>
import vanCard from "@/wxcomponents/vant/dist/card";
export default {
    name:'media',
    data(){
        return {
            value: '',
            tabs: [
                {
                    title: "中文",
                    desc: "优秀中文绘本",
                    productTitle: "三只小猪",
                    thumb:'https://img.yzcdn.cn/upload_files/2017/07/02/af5b9f44deaeb68000d7e4a711160c53.jpg'
                },
                {                    
                    title: "英文",
                    desc: "优秀英文绘本",
                    productTitle: "石头汤",
                    thumb:'https://img.yzcdn.cn/upload_files/2017/07/02/af5b9f44deaeb68000d7e4a711160c53.jpg'
                },
                {
                    
                    title: "经典",
                    desc: "经典绘本",
                    productTitle: "猜猜我有多爱你",
                    thumb:'https://img.yzcdn.cn/upload_files/2017/07/02/af5b9f44deaeb68000d7e4a711160c53.jpg'
                }
            ]
        };
    },
    methods:{   
        changeBookType(event){
            //wx.showToast({
                //title: this.tabs[event.detail.index].title
            //})
        }    
    },
    components:{  
        vanCard    
    }
}
</script>
<style>
.content {
    background-color: #fefefe 
}

.input-box {
    border-bottom: 1px solid rgba(153, 204, 255, .2)
}

.van-search__content {
    /* border: 1px solid red; */
}
.book-grid {
    box-shadow: 1px 1px 2px rgba(204,204,204, .5);
}
.book-category {
    margin-top:10px;
}
.van-tabs__nav{
    border-bottom: 1px solid #e7d8d8;
}
.van-tabs__content{
    padding:10px;
    margin-top:10px;
    
}

</style>
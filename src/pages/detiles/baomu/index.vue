<template>
  <div class="detiles-wrapper">
    <div class="server-img-wrapper">
      <img :src="imgTitle" alt="">
    </div>
    <div class="contexr-wrapper">
      <div class="server-introduce-wrapper contexr-wrapper-items">
        <div class="introduce-title"><i class="icons"></i>服务介绍</div>
        <div class="introduce-detiles contexr-detiles">
          家维精心挑选专业保姆，拥有丰富服务经验，为客户提供日常保洁、洗衣、做饭的能全方位生活服务。用户根据自身需求，灵活选择住家或不住家保姆。专业管家服务，尽享品质生活。
        </div>
      </div>
      <div class="server-price-wrapper contexr-wrapper-items">
        <div class="price-title"><i></i><div class="tab-click" :class="{active:activeId==0,'':activeId==1}" @click="switchTab(0)">日常料理</div><div class="tab-click" :class="{active:activeId==1,'':activeId==0}"  @click="switchTab(1)">老人养护</div></div>
        <div class="price-detiles-tab">
          <div class="price-detiles"  v-if="activeShow">
            <div class="price-items">
              <div class="price-lever">住家保</div>
              <div class="price-hour">
                <span style="color:#467fcd;font-size: 20px">￥5300</span>/每月
              </div>
              <div class="price-type">随时为您提供优质服务：日常清洁、衣物洗护、三餐制作</div>
            </div>
            <div class="price-items">
              <div class="price-lever">非住家保</div>
              <div class="price-hour">
                <span style="color:#467fcd;font-size: 20px">￥5000</span>/每月
              </div>
              <div class="price-type">为您提供一下优质服务：日常清洁、衣物洗护、三餐制作</div>
            </div>
          </div>
          <div class="price-detiles" v-if="!activeShow">
            <div class="price-items">
              <div class="price-lever">住家保</div>
              <div class="price-hour">
                <span style="color:#467fcd;font-size: 20px">￥6300</span>/每月
              </div>
              <div class="price-type">随时为您提供优质服务：日常清洁、衣物洗护、三餐制作</div>
            </div>
            <div class="price-items">
              <div class="price-lever">非住家保</div>
              <div class="price-hour">
                <span style="color:#467fcd;font-size: 20px">￥6000</span>/每月
              </div>
              <div class="price-type">为您提供一下优质服务：日常清洁、衣物洗护、三餐制作</div>
            </div>
          </div>
        </div>
      </div>
      <div class="server-range-wrapper contexr-wrapper-items">
        <div class="introduce-title range-title"><i></i>服务范围</div>
        <div class="range-detiles contexr-detiles">
          <div class="range-items" v-for="(items,index) in rangeData">
            <div class="range-img">
              <img :src="items.urls" alt="">
            </div>
            <div class="range-context">
              <p>{{items.value}}</p>
              <p>{{items.valueSub}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="yuding">立即预定</div>
  </div>
</template>

<script>
  import imgTitle from 'static/tabs/baomu/bm@2x.png'
  import imgRange1 from 'static/tabs/baomu/bm1@3x.png'
  import imgRange2 from 'static/tabs/baomu/bm1@3x.png'
  export default {

    components: {
    },
    data () {
      return {
        imgTitle:imgTitle,
        activeId:0,
        activeShow:true,
        rangeData:[
          {
            urls:imgRange1,
            value:'家居保洁',
            valueSub:'家庭保洁、衣物洗涤保养'
          },
          {
            urls:imgRange2,
            value:'家庭餐制作',
            valueSub:'烹饪美味佳肴'
          }

        ]
      }
    },
    created () {

    },
    methods:{
      switchTab(index){
        this.activeId = index;
        if(index==0){
          this.activeShow = true
        }else{
          this.activeShow = false
        }
      }
    },
    onLoad() {
      console.log("onlo")
      wx.setNavigationBarTitle({
        title: '开荒服务'
      })
    },

  }
</script>

<style scoped>
  .server-img-wrapper{
    width: 100%;
    height: 390rpx;
  }
  .server-img-wrapper img{
    width:100%;
    height: 100%;
  }
  .server-introduce-wrapper i{
    display: inline-block;
    width: 14px;
    height: 14px;
    background: url("~static/tabs/common/introduce@2x.png") no-repeat center center;
    background-size: contain;
    margin-right: 7px;
  }
  .server-price-wrapper i{
    display: inline-block;
    width: 14px;
    height: 14px;
    background: url("~static/tabs/common/money@2x.png") no-repeat center center;
    background-size: contain;
    margin-right: 7px;
  }
  .server-range-wrapper i{
    display: inline-block;
    width: 14px;
    height: 14px;
    background: url("~static/tabs/common/service@2x.png") no-repeat center center;
    background-size: contain;
    margin-right: 7px;
  }
  .contexr-wrapper{
    width: 100%;
    box-sizing: border-box;
    padding: 20px 15px;
  }
  .server-range-wrapper{
    width: 100%;
  }
  .range-items img{

  }
  .contexr-wrapper-items{
    width: 100%;
    padding: 18px;
    box-sizing: border-box;
    background: #ffffff;
    box-shadow:  0 4px 4px 1px rgba(231,236,250,1);
    margin-bottom: 13px;
    display: flex;
    flex-direction: column;
  }
  .contexr-detiles{
    flex:1;
    font-size: 14px;
    line-height: 24px;
    color: #959595;
    padding-top:15px ;
  }
  .introduce-title{
    border-bottom: 2px solid #eaeaea;
    padding-bottom: 10px;
    display: flex;
    align-items: center;
  }
  .range-detiles{
    display: flex;
    flex-wrap: wrap;
  }
  .range-items{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 50%;
    margin-bottom: 28px;
  }
  .range-items img{
    width: 105px;
    height:105px;
  }
  .range-context{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  /*服务价格*/
  .price-detiles-tab{
    flex:1;
  }
  .price-detiles{
    flex-direction: column;
    width: 100%;
    display:flex ;
  }
  .price-items{
    display: flex;
    flex-direction: column;
    flex: 1;
    padding: 18px 0;
    margin-bottom: 12px;
    background: #f8f9f9;
  }
  .price-type{
    font-size: 12px;
    color: #959595;
    padding-left: 22px;
  }
  .price-type-unit{
    background: #c29962;
    color: #fff;
    border-radius: 5px;
  }
  .yuding{
    font-size: 16px;
    margin: 20px 28px;
    margin-top: -10px;
    width: calc( 100% - 56px);
    height: 45px;
    text-align: center;
    cursor: pointer;
    color: #fff;
    line-height: 45px;
    background: #c29962;
  }
  .price-hour{
    padding-left: 22px;
    margin-bottom: 9px;
  }
  .price-lever{
    font-size: 18px;
    font-weight: bolder;
    color: #333333;
    box-sizing: border-box;
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  }
  .price-lever:before{
    content: "";
    display: inline-block;
    height: 18px;
    width: 5px;
    background: #aaaaaa;
    margin-right:17px ;
  }
  /*tab切换样式*/
  .tab-click{
    width: 70px;
    text-align: center;
    font-size: 14px;
    color: #aaaaaa;
  }
  .tab-click.active{
    color: #333333;
    border-bottom: 2px solid #fa4b70;
  }
  .tab-click:nth-child(2){
    margin-right: 75px;
    margin-left: 12px;
  }
  .price-title{
    border-bottom: 2px solid #eaeaea;
    height: 36px;
    line-height: 36px;
    display: flex;
    align-items: center;
  }
</style>

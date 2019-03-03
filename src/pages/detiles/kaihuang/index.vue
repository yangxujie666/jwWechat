<template>
  <div class="detiles-wrapper">
    <div class="server-img-wrapper">
      <img :src="imgTitle" alt="">
    </div>
    <div class="contexr-wrapper">
      <div class="server-introduce-wrapper contexr-wrapper-items">
        <div class="introduce-title"><i class="icons"></i>服务介绍</div>
        <div class="introduce-detiles contexr-detiles">
          家维家政为您提供高品质的空房新居开荒服务，帮您彻底清除房屋装修时产生的灰尘、胶点、漆电荷水泥等装修痕迹，快速入住新居。
        </div>
      </div>
      <div class="server-price-wrapper contexr-wrapper-items">
        <div class="introduce-title price-title"><i></i>开荒价格</div>
        <div class="price-detiles">
          <div class="price-items">
            <div class="price-lever">粗开</div>
            <div class="price-hour">
              <span style="color:#467fcd;font-size: 20px">￥4</span><span style="color: #adadad;font-size: 16px;">/平米</span>
            </div>
            <div class="price-type">快速彻底清除装修痕迹<br/>(需根据客户提供的信息实地考察-按建筑面积算)</div>
          </div>
          <div class="price-items">
            <div class="price-lever">精开</div>
            <div class="price-hour">
              <span style="color:#fa4b70;font-size: 20px">￥6</span><span style="color: #adadad;font-size: 16px;">/平米</span>
            </div>
            <div class="price-type">清除卫生死角，省时省力<br/>(需根据客户提供的信息实地考察-按建筑面积算)</div>
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
  import imgTitle from 'static/tabs/kaihuang/kh@2x.png'
  import imgRange1 from 'static/tabs/kaihuang/kh1@3x.png'
  import imgRange2 from 'static/tabs/kaihuang/kh2@3x.png'

  export default {

    components: {
    },
    data () {
      return {
        imgTitle:imgTitle,
        rangeData:[
          {
            urls:imgRange1,
            value:'新居开荒',
            valueSub:'清除痕迹，快速入住'
          },
          {
            urls:imgRange2,
            value:'写字楼开荒',
            valueSub:'专业工具，熟练操作'
          }
        ]
      }
    },
    created () {

    },
    methods:{

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
  .price-detiles{
    display: flex;
    flex-direction: column;
    width: 100%;
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
</style>

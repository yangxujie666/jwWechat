<template>
  <div class="detiles-wrapper">
    <div class="server-img-wrapper">
      <img :src="imgTitle" alt="">
    </div>
    <div class="contexr-wrapper">
      <div class="server-introduce-wrapper contexr-wrapper-items">
        <div class="introduce-title"><i class="icons"></i>服务介绍</div>
        <div class="introduce-detiles contexr-detiles">
          家维家政致力于为婴儿提供起居照顾、婴儿喂养、早期教育、行为培养、婴儿健康等专业的服务。
        </div>
      </div>
      <div class="server-price-wrapper contexr-wrapper-items">
        <div class="introduce-title price-title"><i></i>服务价格</div>
        <div class="price-detiles">
          <div class="price-items">
            <div class="price-lever">高级</div>
            <div class="price-hour">
              <span style="color:#467fcd;font-size: 20px">￥7500</span><span style="color: #adadad;font-size: 16px;">/每月</span>
            </div>
            <div class="price-type">6-36个月宝宝的生长发育</div>
          </div>
          <div class="price-items">
            <div class="price-lever">金牌</div>
            <div class="price-hour">
              <span style="color:#fa4b70;font-size: 20px">￥8500</span><span style="color: #adadad;font-size: 16px;">/每月</span>
            </div>
            <div class="price-type">1-6个月小婴，以及宝宝的生长发育，宝马的恢复指导</div>
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
  import imgTitle from 'static/tabs/yuersao/child@2x.png'
  import imgRange1 from 'static/tabs/yuersao/child1@3x.png'
  import imgRange2 from 'static/tabs/yuersao/child2@3x.png'
  import imgRange3 from 'static/tabs/yuersao/child3@3x.png'
  import imgRange4 from 'static/tabs/yuersao/child4@3x.png'
  export default {

    components: {
    },
    data () {
      return {
        imgTitle:imgTitle,
        rangeData:[
          {
            urls:imgRange1,
            value:'婴儿喂养',
            valueSub:'协助母婴喂养'
          },
          {
            urls:imgRange2,
            value:'起居照顾',
            valueSub:'清洗打扫婴儿居室'
          },
          {
            urls:imgRange3,
            value:'早期教育',
            valueSub:'语言交流，潜能开发'
          },
          {
            urls:imgRange4,
            value:'行为培养',
            valueSub:'良好习惯培养'
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
        title: '育儿嫂服务'
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

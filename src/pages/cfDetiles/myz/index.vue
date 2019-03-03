<template>
  <div class="detiles-wrapper">
    <div>
      <div class="server-img-wrapper">
        <img :src="imgTitle" alt="">
      </div>
      <div class="contexr-wrapper">
        <div class="server-introduce-wrapper contexr-wrapper-items">
          <div class="introduce-title"><i class="icons"></i>服务介绍</div>
          <div class="introduce-detiles contexr-detiles">
            满月照服务详情介绍，满月照服务详情介绍，满月照服务详情介绍，满月照服务详情介绍
          </div>
        </div>
        <div class="server-price-wrapper contexr-wrapper-items">
          <div class="introduce-title price-title"><i></i>服务价格</div>
          <div class="price-detiles contexr-detiles">
            <div class="price-items">
              <div class="price-hour">
                <span style="color:#467fcd;font-size: 20px">￥698</span><span style="color: #adadad;font-size: 16px;">起/次</span>
              </div>
              <div class="price-type">到店价格</div>
            </div>
            <div class="price-items">
              <div>
                <span style="color:#fa4b70;font-size: 20px">￥698</span><span style="color: #adadad;font-size: 16px;">起/次</span>
              </div>
              <div class="price-type price-type-unit">上门价格</div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="yuding">立即预定</div>
  </div>
</template>

<script>
  import imgTitle from 'static/tabs/cfDetiles/myz@2x.png'

  export default {

    components: {
    },
    data () {
      return {
        imgTitle:imgTitle
      }
    },
    created () {

    },
    methods:{

    },
    onLoad() {
      console.log("onlo")
      wx.setNavigationBarTitle({
        title: '满月照'
      })
    },

  }
</script>

<style scoped>
  .detiles-wrapper{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 100vw;
    height: 100vh;
  }
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

  .range-items img{
    width: 105px;
    height:105px;
  }

  /*服务价格*/
  .price-detiles{
    display: flex;
    width: 100%;
  }
  .price-items{
    display: flex;
    flex-direction: column;
    flex: 1;
    align-items: center;
    justify-content: center;
  }
  .price-type{
    font-size: 12px;
    color: #959595;
    margin-top: 5px;
    padding:2px 6px;
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
</style>

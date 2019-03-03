<template>
  <div class="detiles-wrapper">
    <div class="contexr-wrapper">
      <div class="server-range-wrapper contexr-wrapper-items">
        <div class="range-detiles contexr-detiles">
          <div class="range-items" :class="{active:activeId == index,'':activeId != index}" v-for="(items,index) in rangeData" @click="switchDetiles(index)">
            <div class="range-img">
              <span class="img-bg"></span>
            </div>
            <div class="range-context">
              <p>{{items.value}}</p>
              <p>{{items.valueSub}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import imgRange1 from 'static/tabs/chanfu/kr1@3x.png'
  import imgRange2 from 'static/tabs/chanfu/cr@3x.png'
  import imgRange3 from 'static/tabs/chanfu/myh@3x.png'
  import imgRange4 from 'static/tabs/chanfu/chxf@3x.png'
  import imgRange5 from 'static/tabs/chanfu/yezs@3x.png'
  import imgRange6 from 'static/tabs/chanfu/myz@3x.png'
  export default {

    components: {
    },
    data () {
      return {
        activeId:0,
        rangeData:[
          {
            urls:imgRange1,
            value:'开乳',
            valueSub:'孕期跟踪，母乳喂养'
          },
          {
            urls:imgRange2,
            value:'催乳',
            valueSub:'手法催乳，轻柔无痛'
          },
          {
            urls:imgRange3,
            value:'满月汗',
            valueSub:'排湿驱寒，增强免疫'
          },
          {
            urls:imgRange4,
            value:'产后恢复',
            valueSub:'缓解阴道松弛和子宫脱垂'
          },
          {
            urls:imgRange5,
            value:'育儿知识',
            valueSub:'科学护理，护航宝宝健康'
          },
          {
            urls:imgRange6,
            value:'满月照',
            valueSub:'经典形象，定格美好瞬间'
          }
        ]
      }
    },
    created () {

    },
    mounted(){

    },
    methods:{
      switchDetiles(index){
        var url;
        if(index == 0){
          url = '../../cfDetiles/kr/main'
        }else if(index == 1){
          url = '../../cfDetiles/cr/main'
        }else if(index == 2){
          url = '../../cfDetiles/myh/main'
        }else if(index == 3){
          url = '../../cfDetiles/chxf/main'
        }else if(index == 4){
          url = '../../cfDetiles/yezs/main'
        }else if(index == 5){
          url = '../../cfDetiles/myz/main'
        }
        mpvue.navigateTo({ url })
      }
    },
    onLoad() {
      console.log("onlo")
      wx.setNavigationBarTitle({
        title: '产妇服务'
      })
      this.activeId = 0;
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
  }
  .server-range-wrapper{
    width: 100%;
  }
  /*模块背景图*/
  .range-items .range-img{
    width: 60px;
    height: 60px;
    border-radius: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 12px;
  }
  .range-items.active{
    background: #337ffe;
    color: #fff!important;
  }

  .range-items .img-bg{
    width: 30px;
    height: 30px;
  }
  .range-items:nth-child(1) .range-img{
    background: #f7d9fd;
  }
  .range-items:nth-child(2) .range-img{
    background: #fff2f2;
  }
  .range-items:nth-child(3) .range-img{
    background: #e7f1fc;
  }
  .range-items:nth-child(4) .range-img{
    background: #fef6e3;
  }
  .range-items:nth-child(5) .range-img{
    background: #f2eaff;
  }
  .range-items:nth-child(6) .range-img{
    background: #ebffea;
  }
  .range-items:nth-child(1) .img-bg{
    background: url("~static/tabs/chanfu/kr@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(1).active .img-bg{
    background: url("~static/tabs/chanfu/kr1@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(2) .img-bg{
    background:  url("~static/tabs/chanfu/cr@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(2).active .img-bg{
    background:  url("~static/tabs/chanfu/cr1@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(3) .img-bg{
    background:  url("~static/tabs/chanfu/myh@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(3).active .img-bg{
    background:  url("~static/tabs/chanfu/myh1@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(4) .img-bg{
    background:  url("~static/tabs/chanfu/chxf@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(4).active .img-bg{
    background:  url("~static/tabs/chanfu/chxf1@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(5) .img-bg{
    background:  url("~static/tabs/chanfu/yezs@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(5).active .img-bg{
    background:  url("~static/tabs/chanfu/yezs1@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(6) .img-bg{
    background:  url("~static/tabs/chanfu/myz@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items:nth-child(6).active .img-bg{
    background:  url("~static/tabs/chanfu/myz1@3x.png") no-repeat center center;
    background-size: contain;
  }
  .range-items.active .range-img{
    background: #71a3fe;
  }
  .contexr-wrapper-items{
    width: 100%;
    padding: 18px;
    box-sizing: border-box;
    background: #ffffff;
    display: flex;
    flex-direction: column;
    padding-bottom: 0;
  }
  .contexr-detiles{
    flex:1;
    font-size: 14px;
    line-height: 24px;
    color: #959595;
    padding-top:15px ;
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
    margin-bottom: 16px;
    background: #ffffff;
    box-shadow:  0 4px 4px 1px rgba(231,236,250,1);
    border-radius: 5px;
    height: 180px;
    width: calc(50% - 8px);
  }
  .range-items:nth-child(odd){
    margin-right: 15px;
  }
  .range-context{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

</style>

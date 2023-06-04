<template>
  <div class="home">
    <section class="topbar">
      <div class="left">
        <img src="@/assets/images/admin.png" alt="" />
        <span>admin</span>
      </div>

      <span class="name"> 实时交易数据监控平台 </span>

      <span class="right">
        {{ currentTime }}
      </span>
    </section>

    <section class="container">
      <div class="left">
        <BusinessData />
        <GoodsVolume />
        <RegistrationStatus />
      </div>
      <div class="center">
        <div class="center_data">
          <div class="item">
            <span class="value">
              <countTo
                :startVal="0"
                :endVal="4969.99"
                :duration="1500"
                :decimals="2"
              ></countTo>
            </span>
            <span class="label"> 交易额(万元) </span>
          </div>

          <div class="item">
            <span class="value">
              <countTo
                :startVal="0"
                :endVal="4969.99"
                :duration="1500"
                :decimals="2"
              ></countTo>
            </span>
            <span class="label"> 交易重量(吨) </span>
          </div>
        </div>

        <Map />
      </div>
      <div class="right">
        <RealtimeData />
        <CustomerVolume />
      </div>
    </section>
  </div>
</template>

<script>
import moment from 'moment'
import BusinessData from '@/views/components/business-data.vue'
import GoodsVolume from '@/views/components/goods-volume.vue'
import RealtimeData from '@/views/components/realtime-data.vue'
import RegistrationStatus from '@/views/components/registration-status.vue'
import CustomerVolume from '@/views/components/customer-volume.vue'
import Map from '@/views/components/map.vue'

import countTo from 'vue-count-to'

export default {
  name: 'Home',

  components: {
    BusinessData,
    RealtimeData,
    GoodsVolume,
    RegistrationStatus,
    CustomerVolume,
    countTo,
    Map
  },

  data () {
    return {
      currentTime: '',
      timer: null
    }
  },

  created () {
    this.currentTime = moment().format('YYYY-MM-DD HH:mm:ss') // 初始化当前时间
    this.timer = setInterval(() => {
      this.currentTime = moment().format('YYYY-MM-DD HH:mm:ss') // 每秒更新当前时间
    }, 1000)
  },

  beforeDestroy () {
    clearInterval(this.timer) // 清除定时器
  }
}
</script>

<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100%;
  background: url('~@/assets/images/bj.jpg') no-repeat;
  background-size: 100% 100%;
  display: flex;
  flex-direction: column;
  align-items: center;

  .topbar {
    position: relative;
    width: 1900px;
    height: 96px;
    display: flex;
    align-items: center;
    justify-content: center;

    .left {
      position: absolute;
      top: 29px;
      left: 23px;
      display: flex;
      align-items: center;

      img {
        height: 21px;
        margin-right: 13px;
      }

      span {
        font-size: 16px;
        font-family: Microsoft YaHei;
        font-weight: 400;
        color: rgba(255, 255, 255, 0.7);
      }
    }

    .name {
      position: absolute;
      top: 6px;
      font-size: 44px;
      font-family: YouSheBiaoTiHei;
      font-weight: 400;

      background: linear-gradient(
        to bottom,
        rgba(255, 255, 255, 1),
        rgba(233, 248, 255, 1),
        rgba(119, 186, 255, 1)
      );
      background-clip: text;
      -webkit-background-clip: text; /* 兼容性支持，适用于WebKit内核浏览器（如Chrome、Safari） */
      color: transparent;
    }

    .right {
      position: absolute;
      top: 33px;
      right: 23px;
      font-size: 16px;
      font-family: Microsoft YaHei;
      font-weight: 400;
      color: rgba(255, 255, 255, 0.7);
    }
  }

  .container {
    flex: 1 0;
    width: 100%;
    padding: 0 38px 43px;
    display: flex;
    overflow: hidden;

    .left {
      width: 403px;
      height: 100%;
      display: grid;
      grid-template-rows: repeat(3, 1fr);
      grid-row-gap: 16px;
      overflow: hidden;
    }

    .center {
      position: relative;
      flex: 1 0;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;

      .center_data {
        position: absolute;
        top: 0;
        display: flex;
        align-items: center;

        .item {
          width: 224px;
          height: 100px;
          display: flex;
          flex-direction: column;
          align-items: center;
          justify-content: center;

          .value {
            font-size: 34px;
            font-family: D-DIN Exp;
            font-weight: bold;
            color: #3193f8;
          }

          .label {
            font-size: 16px;
            font-family: Microsoft YaHei;
            font-weight: 400;
            color: #ffffff;
            margin-top: 8px;
          }

          &:nth-child(1) {
            border-top: 1px solid rgba(33, 143, 247, 1);
            background: linear-gradient(
              to bottom,
              rgba(33, 143, 247, 0.2),
              rgba(33, 143, 247, 0)
            );
            margin-right: 18px;
          }

          &:nth-child(2) {
            border-top: 1px solid rgba(144, 255, 173, 1);
            background: linear-gradient(
              to bottom,
              rgba(144, 255, 173, 0.2),
              rgba(144, 255, 173, 0)
            );

            .value {
              color: rgba(144, 255, 173, 1);
            }
          }
        }
      }
    }

    .right {
      width: 403px;
      height: 100%;
      display: grid;
      grid-template-rows: repeat(2, 1fr);
      grid-row-gap: 16px;
      overflow: hidden;
    }
  }
}
</style>

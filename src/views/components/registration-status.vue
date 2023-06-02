<template>
  <div class="registration-status">
    <Box title="个体户注册情况">
      <section class="container">
        <div class="item">
          <div class="imgs">
            <img src="@/assets/images/base.png" alt="" />
            <img src="@/assets/images/park.png" alt="" />
          </div>
          <span class="label"> 一号园区 </span>
          <span class="value">
            <countTo
              :startVal="0"
              :endVal="589"
              :duration="1500"
              :decimals="0"
            ></countTo>
          </span>
        </div>

        <div class="item">
          <div class="imgs">
            <img src="@/assets/images/base.png" alt="" />
            <img src="@/assets/images/park.png" alt="" />
          </div>
          <span class="label"> 二号园区 </span>
          <span class="value">
            <countTo
              :startVal="0"
              :endVal="589"
              :duration="1500"
              :decimals="0"
            ></countTo>
          </span>
        </div>
      </section>
    </Box>
  </div>
</template>

<script>
import countTo from 'vue-count-to'

import Box from '@/components/box.vue'

export default {
  name: 'RegistrationStatus',

  components: {
    Box,
    countTo
  }
}
</script>

<style lang="scss" scoped>
.registration-status {
  width: 100%;
  height: 100%;

  .container {
    width: 100%;
    height: 100%;
    display: flex;

    .item {
      flex: 1 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;

      .imgs {
        position: relative;
        width: 123px;
        height: 109px;
        display: flex;
        align-items: center;
        justify-content: center;

        img {
          position: absolute;
          &:nth-child(1) {
            width: 123px;
            height: 109px;
          }

          &:nth-child(2) {
            margin-bottom: 40px;
            animation: mb1 3s linear infinite;
          }

          @keyframes mb1 {
            0% {
              margin-bottom: 40px;
            }
            50% {
              margin-bottom: 80px;
            }
            100% {
              margin-bottom: 40px;
            }
          }
        }
      }

      .label {
        font-size: 16px;
        font-family: Microsoft YaHei;
        font-weight: 400;
        color: #ffffff;
        margin-top: 11px;
      }

      .value {
        font-size: 25px;
        font-family: Microsoft YaHei;
        font-weight: 400;
        color: rgba(49, 147, 248, 1);
        margin-top: 8px;
      }

      &:nth-child(2) {
        .imgs {
          img {
            &:nth-child(2) {
              margin-bottom: 80px;
              animation: mb2 3s linear infinite;
            }

            @keyframes mb2 {
              0% {
                margin-bottom: 80px;
              }
              50% {
                margin-bottom: 40px;
              }
              100% {
                margin-bottom: 80px;
              }
            }
          }
        }

        .value {
          color: rgba(144, 255, 173, 1);
        }
      }
    }
  }
}
</style>

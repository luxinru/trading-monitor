<template>
  <div class="xtable">
    <table>
      <thead>
        <tr>
          <th v-for="(item, index) in columns" :key="index">
            {{ item.label }}
          </th>
        </tr>
      </thead>
      <tbody ref="body">
        <template v-if="list.length">
          <tr v-for="(item, i) in list" :key="i">
            <td
              v-for="(column, j) in columns"
              :key="j"
              :class="{ tdclass: j === 0 && item[column.value].length > 5 }"
            >
              <span
                :class="{ scroll: j === 0 && item[column.value].length > 5 }"
              >
                {{ item[column.value] }}
              </span>
            </td>
          </tr>
        </template>

        <template v-else>
          <span class="nodata">暂无数据</span>
        </template>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'XTable',

  props: {
    list: {
      type: Array,
      default: () => [
        {
          label1: '供应商名称',
          label2: '江淮重卡',
          label3: '品类1',
          label4: '5',
          label5: '1548'
        }
      ]
    },
    columns: {
      type: Array,
      default: () => [
        {
          label: '供应商',
          value: 'label1'
        },
        {
          label: '车辆',
          value: 'label2'
        },
        {
          label: '商品品类',
          value: 'label3'
        },
        {
          label: '重量',
          value: 'label4'
        },
        {
          label: '金额',
          value: 'label5'
        }
      ]
    }
  },

  data () {
    return {
      timer: null
    }
  },

  mounted () {
    this.$nextTick(() => {
      this.autoPlay()
    })
  },

  beforeDestroy () {
    window.clearInterval(this.timer)
  },

  methods: {
    autoPlay () {
      console.log('object :>> ', [this.$refs.body])
      const { clientHeight, scrollHeight } = this.$refs.body
      if (scrollHeight > clientHeight) {
        // 表格内容区域自动滚动
        this.timer = setInterval(() => {
          this.$refs.body.scrollTop += 1

          if (this.$refs.body.scrollTop === scrollHeight - clientHeight) {
            this.$refs.body.scrollTop = 0
          }
        }, 50)
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.xtable {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;

  table {
    width: 100%;
    height: 100%;
    position: relative;
    display: flex;
    flex-direction: column;
    overflow: hidden;

    thead {
      position: sticky;
      top: 0;
      width: 100%;
      height: 33px;
      background: rgba(98, 98, 98, 0);

      tr {
        background: url('~@/assets/images/frame.png') no-repeat;
        background-size: 100% 100%;

        th {
          &:last-child {
            margin-right: 4px;
          }
        }
      }
    }

    tbody {
      width: 100%;
      flex: 1 0;
      overflow-y: auto;

      tr {
        margin-top: 2px;
        background: url('~@/assets/images/frame-1.png') no-repeat;
        background-size: 100% 100%;
      }

      .nodata {
        width: 100%;
        height: 100%;
        font-size: 12px;
        font-family: Microsoft YaHei;
        font-weight: 400;
        color: rgba(238, 238, 238, 1);
        display: flex;
        align-items: center;
        justify-content: center;
      }
    }

    tr {
      width: 100%;
      height: 33px;
      display: flex;
      align-items: center;
      padding: 0 15px;

      th,
      td {
        flex: 1 0;
        overflow: hidden;
      }

      th {
        font-size: 14px;
        font-family: Microsoft YaHei;
        font-weight: 400;
        color: #ffffff;
        display: flex;
        align-items: center;
        justify-content: center;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }

      td {
        font-size: 13px;
        font-family: Microsoft YaHei;
        font-weight: 400;
        color: #3193f8;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
      }

      .tdclass {
        justify-content: flex-start;
      }

      .scroll {
        white-space: nowrap; /* 避免文本换行 */
        animation: scroll 7s linear infinite; /* 使用动画实现自动滚动，5s为滚动时长，可以根据需要调整 */
      }

      @keyframes scroll {
        0% {
          transform: translateX(0);
        }
        40% {
          transform: translateX(0);
        }
        100% {
          transform: translateX(-100%);
        }
      }
    }
  }
}
</style>

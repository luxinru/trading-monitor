<template>
  <div class="customer-volume">
    <Box title="客户交易量" backgroundDirection="right">
      <XTable :list="tableList" :columns="columns" />
    </Box>
  </div>
</template>

<script>
import Box from '@/components/box.vue'
import XTable from '@/components/xtable.vue'

export default {
  name: 'CustomerVolume',

  components: {
    Box,
    XTable
  },

  data () {
    return {
      tableList: [],
      columns: [
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

  created () {
    const result = []
    for (let index = 0; index < 100; index++) {
      result.push({
        label1: '供应商名称',
        label2: '江淮重卡',
        label3: '品类1',
        label4: '5',
        label5: '1548'
      })
    }

    this.tableList = result
  }
}
</script>

<style lang="scss" scoped>
.customer-volume {
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>

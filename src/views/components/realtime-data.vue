<template>
  <div class="realtime-data">
    <Box title="实时交易数据" backgroundDirection="right">
      <XTable :list="tableList" :columns="columns" />
    </Box>
  </div>
</template>

<script>
import Box from '@/components/box.vue'
import XTable from '@/components/xtable.vue'

export default {
  name: 'RealtimeData',

  components: {
    Box,
    XTable
  },

  data () {
    return {
      tableList: [
        {
          label1: '任杰帅',
          label2: '中再宁夏',
          label3: '冀B1192V',
          label4: 35.16,
          label5: 91064.4
        },
        {
          label1: '李桂芝',
          label2: '中再宁夏',
          label3: '京APV809',
          label4: 32.88,
          label5: 83515.2
        },
        {
          label1: '王金鹏',
          label2: '中再宁夏',
          label3: '冀B3622V',
          label4: 11.34,
          label5: 28690.2
        },
        {
          label1: '王宝巨',
          label2: '中再宁夏',
          label3: '冀B0071G',
          label4: 48.58,
          label5: 123879
        },
        {
          label1: '律振堂',
          label2: '中再宁夏',
          label3: '津CE9010',
          label4: 26.4,
          label5: 67584
        },
        {
          label1: '王福建',
          label2: '中再宁夏',
          label3: '冀FZ2585',
          label4: 33.83,
          label5: 84575
        },
        {
          label1: '宋玉苹',
          label2: '中再宁夏',
          label3: '冀B5399Z',
          label4: 42.91,
          label5: 108991.4
        },
        {
          label1: '杨利涛',
          label2: '中再宁夏',
          label3: '冀B9833Z',
          label4: 1.26,
          label5: 2885.4
        },
        {
          label1: '王仁涛',
          label2: '中再宁夏',
          label3: '冀B5002Y',
          label4: 49.88,
          label5: 131184.4
        },
        {
          label1: '孙广雨',
          label2: '中再宁夏',
          label3: '蒙D42347',
          label4: 33.34,
          label5: 85683.8
        },
        {
          label1: '卑利建',
          label2: '中再宁夏',
          label3: '冀B2D377',
          label4: 37.6,
          label5: 97384
        },
        {
          label1: '殷勤',
          label2: '中再宁夏',
          label3: '冀B2C252',
          label4: 31.26,
          label5: 79713
        },
        {
          label1: '黄朝忠',
          label2: '中再安徽',
          label3: '苏NE9298',
          label4: 1.02,
          label5: 2386.8
        },
        {
          label1: '陆虎',
          label2: '中再安徽',
          label3: '皖P54759',
          label4: 7.32,
          label5: 17128.8
        },
        {
          label1: '王宏涛',
          label2: '中再安徽',
          label3: '鲁Q999KD',
          label4: 30.07,
          label5: 73972.2
        },
        {
          label1: '邵星',
          label2: '中再安徽',
          label3: '皖AE9185',
          label4: 24.44,
          label5: 57189.6
        },
        {
          label1: '邵星',
          label2: '中再安徽',
          label3: '皖KR3678',
          label4: 18.4,
          label5: 43056
        },
        {
          label1: '邵星',
          label2: '中再安徽',
          label3: '皖LD6339',
          label4: 11.98,
          label5: 28033.2
        },
        {
          label1: '邵星',
          label2: '中再安徽',
          label3: '鲁Q609JK',
          label4: 23.57,
          label5: 51854
        },
        {
          label1: '马臣',
          label2: '中再安徽',
          label3: '苏BJ9602',
          label4: 24.27,
          label5: 56791.8
        },
        {
          label1: '马臣',
          label2: '中再安徽',
          label3: '皖LD9577',
          label4: 26.9,
          label5: 62946
        },
        {
          label1: '周国刚',
          label2: '中再宁夏',
          label3: '京AZC089',
          label4: 32.14,
          label5: 83242.6
        },
        {
          label1: '黄欢',
          label2: '中再宁夏',
          label3: '冀B1232Z',
          label4: 32.88,
          label5: 84172.8
        },
        {
          label1: '贾海丰',
          label2: '中再宁夏',
          label3: '冀B1SV26',
          label4: 7.22,
          label5: 18338.8
        },
        {
          label1: '詹建民',
          label2: '中再宁夏',
          label3: '冀BM56W5',
          label4: 3.34,
          label5: 8450.2
        },
        {
          label1: '郭兴得',
          label2: '中再宁夏',
          label3: '冀B8365L',
          label4: 10.96,
          label5: 28715.2
        },
        {
          label1: '卢建茹',
          label2: '中再宁夏',
          label3: '京ANQ958',
          label4: 32.04,
          label5: 81061.2
        },
        {
          label1: '董文久',
          label2: '中再宁夏',
          label3: '冀B8221Y',
          label4: 18.6,
          label5: 47244
        },
        {
          label1: '李维星',
          label2: '中再宁夏',
          label3: '冀B6N857',
          label4: 32.72,
          label5: 86053.6
        },
        {
          label1: '赵俊才',
          label2: '中再宁夏',
          label3: '黑EM4978',
          label4: 35.15,
          label5: 91390
        },
        {
          label1: '赵杰',
          label2: '中再宁夏',
          label3: '冀B2V00F',
          label4: 2.25,
          label5: 5782.5
        },
        {
          label1: '李维星',
          label2: '中再宁夏',
          label3: '冀B1890L',
          label4: 32.24,
          label5: 84791.2
        },
        {
          label1: '汪明华',
          label2: '中再宁夏',
          label3: '冀B8003R',
          label4: 33.12,
          label5: 84124.8
        },
        {
          label1: '王连喜',
          label2: '中再宁夏',
          label3: '冀B0K555',
          label4: 31.8,
          label5: 77592
        },
        {
          label1: '王金鹏',
          label2: '中再宁夏',
          label3: '鲁MAN721',
          label4: 12.86,
          label5: 33050.2
        },
        {
          label1: '祝尊杰',
          label2: '中再宁夏',
          label3: '冀B9C082',
          label4: 36.07,
          label5: 92339.2
        },
        {
          label1: '艾福旺',
          label2: '中再宁夏',
          label3: '津C80596',
          label4: 30.98,
          label5: 78379.4
        },
        {
          label1: '杨拓开',
          label2: '中再宁夏',
          label3: '冀FT5566',
          label4: 33.18,
          label5: 85936.2
        },
        {
          label1: '马树东',
          label2: '中再宁夏',
          label3: '冀R81JH8',
          label4: 1.56,
          label5: 4009.2
        },
        {
          label1: '王永海',
          label2: '中再宁夏',
          label3: '冀B1362E',
          label4: 33.2,
          label5: 83996
        },
        {
          label1: '朱华芹',
          label2: '中再宁夏',
          label3: '津CF7377',
          label4: 33.2,
          label5: 85324
        },
        {
          label1: '王焕起',
          label2: '中再宁夏',
          label3: '冀B9F781',
          label4: 17.62,
          label5: 45283.4
        },
        {
          label1: '王焕起',
          label2: '中再宁夏',
          label3: '冀B1826N',
          label4: 9.02,
          label5: 23181.4
        },
        {
          label1: '姬运增',
          label2: '中再宁夏',
          label3: '冀B8AJ93',
          label4: 8.62,
          label5: 23360.2
        },
        {
          label1: '汪明华',
          label2: '中再宁夏',
          label3: '京AGE181',
          label4: 32.26,
          label5: 81940.4
        },
        {
          label1: '朱华芹',
          label2: '中再宁夏',
          label3: '津CH5827',
          label4: 33.7,
          label5: 85261
        },
        {
          label1: '王贺勤',
          label2: '中再宁夏',
          label3: '冀B5J707',
          label4: 38.96,
          label5: 100127.2
        },
        {
          label1: '田永才',
          label2: '中再宁夏',
          label3: '冀B1861X',
          label4: 33.64,
          label5: 87127.6
        },
        {
          label1: '肖建克',
          label2: '中再宁夏',
          label3: '冀B9557M',
          label4: 62.02,
          label5: 158151
        },
        {
          label1: '灵武市中再王雷再生资源回收场',
          label2: '中再常州',
          label3: '苏D80133',
          label4: 5.8,
          label5: 1508
        },
        {
          label1: '灵武市中再梅明再生资源回收场',
          label2: '中再常州',
          label3: '苏DJK132',
          label4: 19.64,
          label5: 15908.4
        },
        {
          label1: '灵武市中再梅明再生资源回收场',
          label2: '中再常州',
          label3: '苏DJK132',
          label4: 19.98,
          label5: 16183.8
        },
        {
          label1: '灵武市中再熊建再生资源回收场',
          label2: '中再常州',
          label3: '皖E20187',
          label4: 36,
          label5: 36000
        },
        {
          label1: '朱海涛',
          label2: '中再洛阳',
          label3: '豫DD02121',
          label4: 0.73,
          label5: 2075
        },
        {
          label1: '吴星星',
          label2: '中再洛阳',
          label3: '豫CV5L07',
          label4: 0.93,
          label5: 1866
        },
        {
          label1: '蔚清洲',
          label2: '中再洛阳',
          label3: '豫C820N3',
          label4: 1.29,
          label5: 3758
        },
        {
          label1: '蔚清洲',
          label2: '中再洛阳',
          label3: '豫CS8C98',
          label4: 1.23,
          label5: 3602
        },
        {
          label1: '蔚清洲',
          label2: '中再洛阳',
          label3: '豫CJK155',
          label4: 0.98,
          label5: 2121
        },
        {
          label1: '王少鹏',
          label2: '中再洛阳',
          label3: '皖CE4057',
          label4: 27.34,
          label5: 75083
        },
        {
          label1: '王梦晓',
          label2: '中再洛阳',
          label3: '豫C769HC',
          label4: 1.13,
          label5: 3066
        },
        {
          label1: '王梦晓',
          label2: '中再洛阳',
          label3: '豫C769HC',
          label4: 1.11,
          label5: 2294
        },
        {
          label1: '王梦晓',
          label2: '中再洛阳',
          label3: '豫C995JC',
          label4: 0.85,
          label5: 2200
        },
        {
          label1: '王梦晓',
          label2: '中再洛阳',
          label3: '豫C769HC',
          label4: 0.85,
          label5: 1898
        },
        {
          label1: '乔丹凤',
          label2: '中再洛阳',
          label3: '豫C778HC',
          label4: 1.08,
          label5: 3036
        },
        {
          label1: '乔丹凤',
          label2: '中再洛阳',
          label3: '豫C769HC',
          label4: 1.07,
          label5: 2960
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '豫CV5L07',
          label4: 1.39,
          label5: 3918
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '豫C778HC',
          label4: 1.11,
          label5: 3164
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '豫C778HC',
          label4: 1.11,
          label5: 3164
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '豫CLJ658',
          label4: 0.86,
          label5: 1869
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '豫C950YN',
          label4: 1.09,
          label5: 3212
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '豫C8K211',
          label4: 0.85,
          label5: 2400
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '豫CV5L07',
          label4: 0.94,
          label5: 1937
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '豫CV5L07',
          label4: 1.13,
          label5: 3216
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '沪C4GY90',
          label4: 1.05,
          label5: 2650
        },
        {
          label1: '柳书琴',
          label2: '中再洛阳',
          label3: '豫CJL983',
          label4: 1.21,
          label5: 3550
        },
        {
          label1: '李佳佳',
          label2: '中再洛阳',
          label3: '豫C778HC',
          label4: 1.09,
          label5: 2812
        },
        {
          label1: '郭亮',
          label2: '中再洛阳',
          label3: '豫C082YH',
          label4: 0.94,
          label5: 2037
        },
        {
          label1: '郭亮',
          label2: '中再洛阳',
          label3: '豫CWS373',
          label4: 1.25,
          label5: 3654
        },
        {
          label1: '郭亮',
          label2: '中再洛阳',
          label3: '豫CJX273',
          label4: 1.12,
          label5: 3200
        },
        {
          label1: '郭亮',
          label2: '中再洛阳',
          label3: '豫C778HC',
          label4: 1.09,
          label5: 3112
        },
        {
          label1: '郭亮',
          label2: '中再洛阳',
          label3: '豫C778HC',
          label4: 1.02,
          label5: 2305
        },
        {
          label1: '郭亮',
          label2: '中再洛阳',
          label3: '无车牌黄奇瑞',
          label4: 0.93,
          label5: 2550
        },
        {
          label1: '郭亮',
          label2: '中再洛阳',
          label3: '无车牌黑奇瑞',
          label4: 1.38,
          label5: 3942
        },
        {
          label1: '窦祎琛',
          label2: '中再洛阳',
          label3: '豫HH5619',
          label4: 24.14,
          label5: 60688.5
        },
        {
          label1: '陈光',
          label2: '中再洛阳',
          label3: '豫C3D207',
          label4: 1.47,
          label5: 3142
        },
        {
          label1: '陈光',
          label2: '中再洛阳',
          label3: '豫C868RZ',
          label4: 0.82,
          label5: 1735
        },
        {
          label1: '高秀平',
          label2: '中再宁夏',
          label3: '蒙B50305',
          label4: 16.96,
          label5: 278696.79
        },
        {
          label1: '灵武市中再舟葳再生资源回收场',
          label2: '中再常州',
          label3: '苏BX2296',
          label4: 36.82,
          label5: 38661
        },
        {
          label1: '段云娥',
          label2: '中再宁夏',
          label3: '冀HN3870',
          label4: 34.86,
          label5: 88195.8
        },
        {
          label1: '于兆民',
          label2: '中再宁夏',
          label3: '冀B0D720',
          label4: 33.2,
          label5: 83664
        },
        {
          label1: '武亚涛',
          label2: '中再宁夏',
          label3: '津CE9010',
          label4: 38.91,
          label5: 96496.8
        },
        {
          label1: '殷勤',
          label2: '中再宁夏',
          label3: '冀B2C252',
          label4: 33.73,
          label5: 83650.4
        },
        {
          label1: '王瑞苓',
          label2: '中再宁夏',
          label3: '冀B5398P',
          label4: 37.06,
          label5: 94132.4
        },
        {
          label1: '马全友',
          label2: '中再宁夏',
          label3: '冀B7397Q',
          label4: 5.87,
          label5: 12914
        },
        {
          label1: '马全友',
          label2: '中再宁夏',
          label3: '冀B7397Q',
          label4: 13.58,
          label5: 34085.8
        },
        {
          label1: '李树平',
          label2: '中再宁夏',
          label3: '冀B9069N',
          label4: 32.68,
          label5: 83334
        },
        {
          label1: '李海军',
          label2: '中再宁夏',
          label3: '冀B9H850',
          label4: 33.8,
          label5: 86190
        },
        {
          label1: '朱会政',
          label2: '中再宁夏',
          label3: '冀B1238U',
          label4: 14.7,
          label5: 36750
        },
        {
          label1: '王宝巨',
          label2: '中再宁夏',
          label3: '冀B0071G',
          label4: 50.84,
          label5: 128625.2
        },
        {
          label1: '王立春',
          label2: '中再宁夏',
          label3: '晋B86159',
          label4: 32.76,
          label5: 82555.2
        },
        {
          label1: '王福建',
          label2: '中再宁夏',
          label3: '京AJD997',
          label4: 31.08,
          label5: 77389.2
        },
        {
          label1: '张联国',
          label2: '中再宁夏',
          label3: '冀B2509Q',
          label4: 33.86,
          label5: 85665.8
        },
        {
          label1: '李根来',
          label2: '中再宁夏',
          label3: '冀B3337V',
          label4: 31.9,
          label5: 79431
        },
        {
          label1: '李根来',
          label2: '中再宁夏',
          label3: '冀B7305M',
          label4: 33.97,
          label5: 84925
        },
        {
          label1: '单万新',
          label2: '中再宁夏',
          label3: '冀B0873R',
          label4: 40.34,
          label5: 102463.6
        },
        {
          label1: '冯杉杉',
          label2: '中再宁夏',
          label3: '冀HR4039',
          label4: 3.86,
          label5: 9572.8
        },
        {
          label1: '王金香',
          label2: '中再宁夏',
          label3: '冀HR4808',
          label4: 32.76,
          label5: 82882.8
        },
        {
          label1: '王康2',
          label2: '中再宁夏',
          label3: '冀B2869Y',
          label4: 31.81,
          label5: 79525
        },
        {
          label1: '袁伟',
          label2: '中再宁夏',
          label3: '津C617D2',
          label4: 6.65,
          label5: 16492
        },
        {
          label1: '冯杉杉',
          label2: '中再宁夏',
          label3: '冀HC1012',
          label4: 34.72,
          label5: 89230.4
        },
        {
          label1: '李风民',
          label2: '中再宁夏',
          label3: '冀GP0399',
          label4: 32.08,
          label5: 79558.4
        },
        {
          label1: '贾海丰',
          label2: '中再宁夏',
          label3: '冀B1SV26',
          label4: 7.74,
          label5: 19272.6
        },
        {
          label1: '王福建',
          label2: '中再宁夏',
          label3: '冀B3726H',
          label4: 33.98,
          label5: 85969.4
        },
        {
          label1: '李风民',
          label2: '中再宁夏',
          label3: '冀GA8859',
          label4: 35.58,
          label5: 90729
        },
        {
          label1: '王福建',
          label2: '中再宁夏',
          label3: '冀B8722U',
          label4: 34.76,
          label5: 86204.8
        },
        {
          label1: '王心好',
          label2: '中再宁夏',
          label3: '鲁MEP021',
          label4: 34.26,
          label5: 85650
        },
        {
          label1: '白俊杰',
          label2: '中再宁夏',
          label3: '冀B8860Z',
          label4: 20.51,
          label5: 55582.1
        },
        {
          label1: '郝东',
          label2: '中再宁夏',
          label3: '冀B6J950',
          label4: 21.38,
          label5: 54732.8
        },
        {
          label1: '韩学丰',
          label2: '中再宁夏',
          label3: '冀BA31W9',
          label4: 5.21,
          label5: 14119.1
        },
        {
          label1: '杨书勇',
          label2: '中再宁夏',
          label3: '鲁MAD569',
          label4: 34.36,
          label5: 87274.4
        },
        {
          label1: '孙会仲',
          label2: '中再宁夏',
          label3: '冀B8H19H',
          label4: 6.65,
          label5: 16492
        },
        {
          label1: '冯庆海',
          label2: '中再宁夏',
          label3: '冀B7P15T',
          label4: 4.68,
          label5: 11466
        },
        {
          label1: '陈宽',
          label2: '中再宁夏',
          label3: '冀CD4070',
          label4: 7.9,
          label5: 20066
        },
        {
          label1: '殷立国',
          label2: '中再宁夏',
          label3: '冀B1Z0X0',
          label4: 12.1,
          label5: 31460
        },
        {
          label1: '茹金',
          label2: '中再宁夏',
          label3: '冀B9W67E',
          label4: 17.79,
          label5: 41628.6
        },
        {
          label1: '郑丛燕',
          label2: '中再洛阳',
          label3: '豫CS7758',
          label4: 12.53,
          label5: 30072
        },
        {
          label1: '艾永娇',
          label2: '中再洛阳',
          label3: '豫C351XT',
          label4: 6.57,
          label5: 15768
        },
        {
          label1: '董利霞',
          label2: '中再洛阳',
          label3: '豫CH9H96',
          label4: 2.18,
          label5: 5079.4
        },
        {
          label1: '郭春明',
          label2: '中再洛阳',
          label3: '豫HG4068',
          label4: 11.61,
          label5: 28792.8
        },
        {
          label1: '杨顺娟',
          label2: '中再洛阳',
          label3: '豫CV5D93',
          label4: 1.96,
          label5: 4566.8
        },
        {
          label1: '万中平',
          label2: '中再洛阳',
          label3: '豫CQ5713',
          label4: 7.47,
          label5: 17928
        },
        {
          label1: '万中平',
          label2: '中再洛阳',
          label3: '豫CN3752',
          label4: 8.28,
          label5: 19872
        },
        {
          label1: '邓玉志',
          label2: '中再洛阳',
          label3: '豫CKV116',
          label4: 2.42,
          label5: 5808
        },
        {
          label1: '郑丛燕',
          label2: '中再洛阳',
          label3: '豫CS7758',
          label4: 11.74,
          label5: 28176
        },
        {
          label1: '苗改革',
          label2: '中再洛阳',
          label3: '豫CP7Z82',
          label4: 5.34,
          label5: 12442.2
        },
        {
          label1: '司欢欢',
          label2: '中再洛阳',
          label3: '豫R306K5',
          label4: 3.11,
          label5: 7464
        },
        {
          label1: '苗密密',
          label2: '中再洛阳',
          label3: '豫C009HQ',
          label4: 3.1,
          label5: 7440
        },
        {
          label1: '艾永娇',
          label2: '中再洛阳',
          label3: '豫C351XT',
          label4: 6.73,
          label5: 16152
        },
        {
          label1: '刘文辉',
          label2: '中再洛阳',
          label3: '豫A6E21X',
          label4: 2.57,
          label5: 5988.1
        },
        {
          label1: '苗改革',
          label2: '中再洛阳',
          label3: '豫CP7Z82',
          label4: 5.86,
          label5: 13653.8
        },
        {
          label1: '郭春明',
          label2: '中再洛阳',
          label3: '豫HM7078',
          label4: 31.48,
          label5: 75552
        },
        {
          label1: '许振潮',
          label2: '中再洛阳',
          label3: '豫CP8U86',
          label4: 3.41,
          label5: 8184
        },
        {
          label1: '岳书荣',
          label2: '中再洛阳',
          label3: '豫CA8W89',
          label4: 6.08,
          label5: 14166.4
        },
        {
          label1: '苗改革',
          label2: '中再洛阳',
          label3: '豫CP7Z82',
          label4: 4.56,
          label5: 10624.8
        },
        {
          label1: '刘文辉',
          label2: '中再洛阳',
          label3: '豫A6E21X',
          label4: 3.66,
          label5: 8527.8
        },
        {
          label1: '李花平',
          label2: '中再洛阳',
          label3: '豫C763CG',
          label4: 3.55,
          label5: 8271.5
        },
        {
          label1: '郭春明',
          label2: '中再洛阳',
          label3: '豫HM7078',
          label4: 28.69,
          label5: 68856
        },
        {
          label1: '郭春明',
          label2: '中再洛阳',
          label3: '豫HM7078',
          label4: 30.65,
          label5: 73560
        },
        {
          label1: '陈永军',
          label2: '中再洛阳',
          label3: '豫CG6789',
          label4: 11.3,
          label5: 26329
        },
        {
          label1: '袁永坡',
          label2: '中再洛阳',
          label3: '豫CP2363',
          label4: 16.57,
          label5: 38608.1
        },
        {
          label1: '畅婉婉',
          label2: '中再洛阳',
          label3: '豫CR3378',
          label4: 3.04,
          label5: 7083.2
        },
        {
          label1: '黄龙龙',
          label2: '中再洛阳',
          label3: '豫CS1626',
          label4: 24.51,
          label5: 58824
        },
        {
          label1: '苗改革',
          label2: '中再洛阳',
          label3: '豫CP7Z82',
          label4: 5.16,
          label5: 12022.8
        },
        {
          label1: '袁秀莲',
          label2: '中再洛阳',
          label3: '豫CF9108',
          label4: 10.76,
          label5: 25070.8
        },
        {
          label1: '葛青茹',
          label2: '中再洛阳',
          label3: '豫CM5239',
          label4: 22.26,
          label5: 53424
        },
        {
          label1: '郭春明',
          label2: '中再洛阳',
          label3: '豫HG4068',
          label4: 11.72,
          label5: 29065.6
        },
        {
          label1: '刘文辉',
          label2: '中再洛阳',
          label3: '豫A6E21X',
          label4: 7.28,
          label5: 16962.4
        },
        {
          label1: '王梦啥',
          label2: '中再洛阳',
          label3: '豫C3961K',
          label4: 5.99,
          label5: 13956.7
        },
        {
          label1: '郑玉乐',
          label2: '中再洛阳',
          label3: '豫CN1385',
          label4: 33.52,
          label5: 89833.6
        },
        {
          label1: '苗改革',
          label2: '中再洛阳',
          label3: '豫D7119L',
          label4: 14.85,
          label5: 39946.5
        },
        {
          label1: '袁世宽',
          label2: '中再洛阳',
          label3: '豫CQ1798',
          label4: 54.96,
          label5: 147842.4
        },
        {
          label1: '张克托',
          label2: '中再洛阳',
          label3: '豫M63175',
          label4: 29.04,
          label5: 78408
        },
        {
          label1: '郑丛燕',
          label2: '中再洛阳',
          label3: '豫CN8807',
          label4: 4.58,
          label5: 12366
        },
        {
          label1: '灵武市中再春旭再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 44.54,
          label5: 60129
        },
        {
          label1: '灵武市中再春旭再生资源回收场',
          label2: '中再常州',
          label3: '皖CE0220',
          label4: 59.32,
          label5: 80082
        },
        {
          label1: '灵武市中再春旭再生资源回收场',
          label2: '中再常州',
          label3: '苏L32277',
          label4: 57.74,
          label5: 77949
        },
        {
          label1: '灵武市中再春旭再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 45.34,
          label5: 61209
        },
        {
          label1: '灵武市中再春旭再生资源回收场',
          label2: '中再常州',
          label3: '皖CE0220',
          label4: 61.12,
          label5: 82512
        },
        {
          label1: '灵武市中再春旭再生资源回收场',
          label2: '中再常州',
          label3: '苏L32277',
          label4: 58.9,
          label5: 79515
        },
        {
          label1: '灵武市中再春旭再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 46.16,
          label5: 62316
        },
        {
          label1: '灵武市中再祝娟再生资源回收场',
          label2: '中再常州',
          label3: '皖CE0220',
          label4: 51.32,
          label5: 69282
        },
        {
          label1: '灵武市中再祝娟再生资源回收场',
          label2: '中再常州',
          label3: '苏L32277',
          label4: 55.98,
          label5: 75573
        },
        {
          label1: '灵武市中再祝娟再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 42.68,
          label5: 57618
        },
        {
          label1: '灵武市中再祝娟再生资源回收场',
          label2: '中再常州',
          label3: '皖CE0220',
          label4: 60.04,
          label5: 81054
        },
        {
          label1: '灵武市中再王雷再生资源回收场',
          label2: '中再常州',
          label3: '鲁DK5270',
          label4: 29.22,
          label5: 7597.2
        },
        {
          label1: '王梦晓',
          label2: '中再洛阳',
          label3: '豫C769HC',
          label4: 1.4,
          label5: 1008
        },
        {
          label1: '灵武市中再柯羽再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 43.36,
          label5: 48042.88
        },
        {
          label1: '灵武市中再柯羽再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 39,
          label5: 43212
        },
        {
          label1: '灵武市中再柯羽再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 41.58,
          label5: 46070.64
        },
        {
          label1: '灵武市中再柯羽再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 42.44,
          label5: 47023.52
        },
        {
          label1: '灵武市中再柯羽再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 42.24,
          label5: 46801.92
        },
        {
          label1: '灵武市中再柯羽再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 43.96,
          label5: 48707.68
        },
        {
          label1: '灵武市中再柯羽再生资源回收场',
          label2: '中再常州',
          label3: '苏L69076',
          label4: 41.78,
          label5: 46292.24
        },
        {
          label1: '灵武市中再柯羽再生资源回收场',
          label2: '中再常州',
          label3: '苏F2302U',
          label4: 19.72,
          label5: 16564.8
        },
        {
          label1: '陈志伟',
          label2: '中再山西',
          label3: '冀B6780Y',
          label4: 14.28,
          label5: 33843.6
        },
        {
          label1: '祝孟富',
          label2: '中再山西',
          label3: '冀B5G037',
          label4: 36.24,
          label5: 76251.2
        },
        {
          label1: '邢致博',
          label2: '中再山西',
          label3: '京ANV623',
          label4: 26.75,
          label5: 59117.5
        },
        {
          label1: '王伟1',
          label2: '中再山西',
          label3: '冀B2M986',
          label4: 39.26,
          label5: 87942.4
        },
        {
          label1: '贾勋超',
          label2: '中再山西',
          label3: '冀B1D555',
          label4: 17.36,
          label5: 42184.8
        },
        {
          label1: '唐勇',
          label2: '中再山西',
          label3: '冀BY85G9',
          label4: 5.79,
          label5: 12564.3
        },
        {
          label1: '张阳',
          label2: '中再山西',
          label3: '冀B3670H',
          label4: 27.2,
          label5: 65280
        },
        {
          label1: '董振利',
          label2: '中再山西',
          label3: '冀BM59B2',
          label4: 5.74,
          label5: 13948.2
        },
        {
          label1: '董振利',
          label2: '中再山西',
          label3: '冀B0G60L',
          label4: 4.02,
          label5: 9728.4
        },
        {
          label1: '郑广民',
          label2: '中再山西',
          label3: '冀J882SY',
          label4: 8.38,
          label5: 18352.2
        },
        {
          label1: '殷学青',
          label2: '中再山西',
          label3: '冀B7B379',
          label4: 32.12,
          label5: 73554.8
        },
        {
          label1: '王艳凤',
          label2: '中再山西',
          label3: '冀B4108L',
          label4: 26.46,
          label5: 61916.4
        },
        {
          label1: '张雪峰',
          label2: '中再山西',
          label3: '鲁MAF399',
          label4: 31.19,
          label5: 74544.1
        },
        {
          label1: '李根来',
          label2: '中再山西',
          label3: '冀B3337V',
          label4: 24.38,
          label5: 52660.8
        },
        {
          label1: '张友军',
          label2: '中再山西',
          label3: '冀B1K990',
          label4: 29.62,
          label5: 66941.2
        },
        {
          label1: '唐醒',
          label2: '中再山西',
          label3: '冀B3296R',
          label4: 27.68,
          label5: 64771.2
        },
        {
          label1: '邢致博',
          label2: '中再山西',
          label3: '冀B8726N',
          label4: 15.28,
          label5: 37436
        },
        {
          label1: '王贺勤',
          label2: '中再山西',
          label3: '冀B2988R',
          label4: 36.38,
          label5: 88767.2
        },
        {
          label1: '王秀静',
          label2: '中再山西',
          label3: '冀B0P706',
          label4: 3.68,
          label5: 7764.8
        },
        {
          label1: '万学云',
          label2: '中再山西',
          label3: '冀B3930L',
          label4: 36.14,
          label5: 86736
        },
        {
          label1: '万学云',
          label2: '中再山西',
          label3: '冀B2A131',
          label4: 27.56,
          label5: 65868.4
        },
        {
          label1: '孙杨',
          label2: '中再山西',
          label3: '冀B5078Y',
          label4: 9.64,
          label5: 21015.2
        },
        {
          label1: '邢致博',
          label2: '中再山西',
          label3: '冀B5087R',
          label4: 30.15,
          label5: 71455.5
        },
        {
          label1: '王春林',
          label2: '中再山西',
          label3: '京AEH877',
          label4: 31.98,
          label5: 76112.4
        },
        {
          label1: '郑小英',
          label2: '中再山西',
          label3: '冀J6Z362',
          label4: 19.88,
          label5: 47314.4
        },
        {
          label1: '杜欢欢',
          label2: '中再山西',
          label3: '冀B3V281',
          label4: 10.44,
          label5: 24847.2
        },
        {
          label1: '王艳凤',
          label2: '中再山西',
          label3: '京APD763',
          label4: 14.55,
          label5: 35793
        },
        {
          label1: '邢致博',
          label2: '中再山西',
          label3: '冀B6040H',
          label4: 20.93,
          label5: 49394.8
        },
        {
          label1: '万学云',
          label2: '中再山西',
          label3: '冀B3013X',
          label4: 22.28,
          label5: 52135.2
        },
        {
          label1: '王俊江',
          label2: '中再山西',
          label3: '津CF7876',
          label4: 7.52,
          label5: 19251.2
        },
        {
          label1: '邢致博',
          label2: '中再山西',
          label3: '冀B1832J',
          label4: 28.47,
          label5: 67758.6
        },
        {
          label1: '詹建民',
          label2: '中再山西',
          label3: '冀BM56W5',
          label4: 2.94,
          label5: 7203
        },
        {
          label1: '柴光敏',
          label2: '中再山西',
          label3: '冀B0999W',
          label4: 28.9,
          label5: 70805
        },
        {
          label1: '黄欢',
          label2: '中再山西',
          label3: '冀B1521E',
          label4: 22.56,
          label5: 53692.8
        },
        {
          label1: '王艳凤',
          label2: '中再山西',
          label3: '冀B3000H',
          label4: 13.41,
          label5: 32854.5
        },
        {
          label1: '张军亮',
          label2: '中再山西',
          label3: '冀B9E281',
          label4: 9.06,
          label5: 19932
        },
        {
          label1: '李云龙',
          label2: '中再山西',
          label3: '冀FP4314',
          label4: 31.84,
          label5: 76097.6
        },
        {
          label1: '赵夺',
          label2: '中再山西',
          label3: '辽NV2276',
          label4: 17.86,
          label5: 39113.4
        },
        {
          label1: '王艳凤',
          label2: '中再山西',
          label3: '津C70261',
          label4: 16.73,
          label5: 37977.1
        },
        {
          label1: '郑翠霞',
          label2: '中再山西',
          label3: '冀HD5825',
          label4: 12.49,
          label5: 30475.6
        },
        {
          label1: '张金玲',
          label2: '中再山西',
          label3: '鲁MGT697',
          label4: 29.2,
          label5: 68328
        },
        {
          label1: '杨海超',
          label2: '中再山西',
          label3: '津C78626',
          label4: 30.88,
          label5: 72876.8
        },
        {
          label1: '万学云',
          label2: '中再山西',
          label3: '冀B9153J',
          label4: 23.03,
          label5: 54811.4
        },
        {
          label1: '杨海超',
          label2: '中再山西',
          label3: '津C73673',
          label4: 25.64,
          label5: 55382.4
        },
        {
          label1: '陈雨利',
          label2: '中再山西',
          label3: '冀BN89E6',
          label4: 4.06,
          label5: 8972.6
        },
        {
          label1: '何肖伟',
          label2: '中再山西',
          label3: '冀B0B937',
          label4: 5.74,
          label5: 14063
        },
        {
          label1: '黄欢',
          label2: '中再山西',
          label3: '冀B3516R',
          label4: 27.24,
          label5: 66738
        },
        {
          label1: '杨铁钢',
          label2: '中再山西',
          label3: '冀B7556Y',
          label4: 11.04,
          label5: 27158.4
        },
        {
          label1: '翟振祥',
          label2: '中再山西',
          label3: '冀B8J261',
          label4: 12.33,
          label5: 16632.8
        },
        {
          label1: '张东江',
          label2: '中再山西',
          label3: '冀B7Z00U',
          label4: 5.78,
          label5: 13525.2
        },
        {
          label1: '吴济飞',
          label2: '中再山西',
          label3: '冀B2F850',
          label4: 10.01,
          label5: 22022
        },
        {
          label1: '郑小英',
          label2: '中再山西',
          label3: '冀B9181Z',
          label4: 5.56,
          label5: 12009.6
        },
        {
          label1: '柴光敏',
          label2: '中再山西',
          label3: '冀B8587H',
          label4: 25.14,
          label5: 61844.4
        },
        {
          label1: '王秀静',
          label2: '中再山西',
          label3: '冀B9P009',
          label4: 7.72,
          label5: 18759.6
        },
        {
          label1: '赵宝金',
          label2: '中再山西',
          label3: '冀B2S713',
          label4: 6.41,
          label5: 15576.3
        },
        {
          label1: '王金华',
          label2: '中再山西',
          label3: '京AWY700',
          label4: 30.3,
          label5: 74235
        },
        {
          label1: '白文云',
          label2: '中再山西',
          label3: '冀B8S313',
          label4: 31.12,
          label5: 76866.4
        },
        {
          label1: '张敬来',
          label2: '中再山西',
          label3: '冀B2EM16',
          label4: 5.93,
          label5: 12512.3
        },
        {
          label1: '吴济飞',
          label2: '中再山西',
          label3: '冀B92XD7',
          label4: 4.5,
          label5: 10935
        },
        {
          label1: '姚海洋',
          label2: '中再山西',
          label3: '京ALX536',
          label4: 11.73,
          label5: 28738.5
        },
        {
          label1: '熊会艳',
          label2: '中再山西',
          label3: '京AVD208',
          label4: 14.83,
          label5: 32477.7
        },
        {
          label1: '孙鹏',
          label2: '中再山西',
          label3: '冀B1C92J',
          label4: 1.23,
          label5: 3001.2
        },
        {
          label1: '黄欢',
          label2: '中再山西',
          label3: '冀B6566H',
          label4: 19,
          label5: 46550
        },
        {
          label1: '刘晓颖',
          label2: '中再山西',
          label3: '鲁MCC927',
          label4: 37.98,
          label5: 91911.6
        },
        {
          label1: '王得强',
          label2: '中再山西',
          label3: '冀B2JX65',
          label4: 6.14,
          label5: 15043
        },
        {
          label1: '李根来',
          label2: '中再山西',
          label3: '冀B0M686',
          label4: 21.79,
          label5: 49681.2
        },
        {
          label1: '宋玉松',
          label2: '中再山西',
          label3: '津CJ3280',
          label4: 24.58,
          label5: 58254.6
        },
        {
          label1: '张洪生',
          label2: '中再山西',
          label3: '冀B0J320',
          label4: 23.52,
          label5: 51744
        },
        {
          label1: '祝尊杰',
          label2: '中再山西',
          label3: '京AEB039',
          label4: 30.8,
          label5: 70224
        },
        {
          label1: '李中伟',
          label2: '中再山西',
          label3: '津C09211',
          label4: 14.19,
          label5: 30934.2
        },
        {
          label1: '万学云',
          label2: '中再山西',
          label3: '冀B1986J',
          label4: 22.58,
          label5: 52837.2
        },
        {
          label1: '殷学青',
          label2: '中再山西',
          label3: '冀B8H599',
          label4: 31.02,
          label5: 68554.2
        },
        {
          label1: '王显义',
          label2: '中再山西',
          label3: '冀B1A986',
          label4: 5.63,
          label5: 11879.3
        },
        {
          label1: '万学云',
          label2: '中再山西',
          label3: '冀B5702H',
          label4: 32.21,
          label5: 77626.1
        },
        {
          label1: '马全友',
          label2: '中再山西',
          label3: '冀B7397Q',
          label4: 7.8,
          label5: 16848
        },
        {
          label1: '王占芹',
          label2: '中再山西',
          label3: '冀BZ0266',
          label4: 3.28,
          label5: 8101.6
        },
        {
          label1: '黄欢',
          label2: '中再山西',
          label3: '京AJP658',
          label4: 28.2,
          label5: 66552
        },
        {
          label1: '吴杰',
          label2: '中再安徽',
          label3: '苏A9C993',
          label4: 29.48,
          label5: 73210.88
        },
        {
          label1: '吴杰',
          label2: '中再安徽',
          label3: '苏A7D161',
          label4: 24.86,
          label5: 60931.86
        },
        {
          label1: '吴杰',
          label2: '中再安徽',
          label3: '苏A2D347',
          label4: 22.34,
          label5: 53874.3
        },
        {
          label1: '吴杰',
          label2: '中再安徽',
          label3: '苏A0D010',
          label4: 19.23,
          label5: 42882.9
        },
        {
          label1: '吴杰',
          label2: '中再安徽',
          label3: '苏A1C636',
          label4: 34.45,
          label5: 86331.7
        },
        {
          label1: '吴杰',
          label2: '中再安徽',
          label3: '苏A7C996',
          label4: 17.63,
          label5: 37058.26
        },
        {
          label1: '吴杰',
          label2: '中再安徽',
          label3: '皖M3B870',
          label4: 29.67,
          label5: 71356.35
        },
        {
          label1: '邓勇',
          label2: '中再安徽',
          label3: '皖P17755',
          label4: 30.42,
          label5: 83046.6
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '皖PA8521',
          label4: 4.59,
          label5: 10740.6
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '苏DBP637',
          label4: 24.31,
          label5: 58100.9
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '苏A9B032',
          label4: 9.35,
          label5: 22346.5
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '苏DBP637',
          label4: 28,
          label5: 65520
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '苏DJC850',
          label4: 3.09,
          label5: 7230.6
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '苏DJK363',
          label4: 13.96,
          label5: 32666.4
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '皖D51968',
          label4: 24.69,
          label5: 57774.6
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '冀D5N275',
          label4: 20.79,
          label5: 48648.6
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '苏CKJ256',
          label4: 23.87,
          label5: 55855.8
        },
        {
          label1: '李凯琼',
          label2: '中再安徽',
          label3: '苏A6B767',
          label4: 9.22,
          label5: 21667
        },
        {
          label1: '邵星',
          label2: '中再安徽',
          label3: '皖KW1366',
          label4: 21.9,
          label5: 52341
        },
        {
          label1: '邵星',
          label2: '中再安徽',
          label3: '皖P18567',
          label4: 21.09,
          label5: 50405.1
        },
        {
          label1: '邵星',
          label2: '中再安徽',
          label3: '豫J90650',
          label4: 26.54,
          label5: 63430.6
        },
        {
          label1: '邵星',
          label2: '中再安徽',
          label3: '皖CA7681',
          label4: 15.83,
          label5: 34826
        },
        {
          label1: '邵星',
          label2: '中再安徽',
          label3: '苏H1977E',
          label4: 25.55,
          label5: 59787
        },
        {
          label1: '江成玉',
          label2: '中再安徽',
          label3: '皖P2C217',
          label4: 38.8,
          label5: 94284
        },
        {
          label1: '公政',
          label2: '中再安徽',
          label3: '皖SB2751',
          label4: 34.66,
          label5: 85956.8
        },
        {
          label1: '公政',
          label2: '中再安徽',
          label3: '皖SC7698',
          label4: 35.14,
          label5: 87147.2
        },
        {
          label1: '公政',
          label2: '中再安徽',
          label3: '皖S27899',
          label4: 35.6,
          label5: 88288
        },
        {
          label1: '公政',
          label2: '中再安徽',
          label3: '苏CDV928',
          label4: 35.14,
          label5: 86093
        },
        {
          label1: '灵武市中再刘钱竹再生资源回收场',
          label2: '中再常州',
          label3: '苏DEX559',
          label4: 35.44,
          label5: 31187.2
        },
        {
          label1: '灵武市中再刘钱竹再生资源回收场',
          label2: '中再常州',
          label3: '苏DJK132',
          label4: 9.52,
          label5: 8377.6
        },
        {
          label1: '灵武市中再刘钱竹再生资源回收场',
          label2: '中再常州',
          label3: '苏DEX559',
          label4: 33.2,
          label5: 29216
        },
        {
          label1: '灵武市中再刘钱竹再生资源回收场',
          label2: '中再常州',
          label3: '闽H56152',
          label4: 32.82,
          label5: 28881.6
        },
        {
          label1: '灵武市中再刘钱竹再生资源回收场',
          label2: '中再常州',
          label3: '苏GN9818',
          label4: 41.08,
          label5: 36150.4
        },
        {
          label1: '陈俊',
          label2: '中再安徽',
          label3: '皖J17983',
          label4: 40,
          label5: 104400
        }
      ],
      columns: [
        {
          label: '供应商',
          value: 'label1'
        },
        {
          label: '归属企业',
          value: 'label2'
        },
        {
          label: '车牌号',
          value: 'label3'
        },
        {
          label: '重量(吨)',
          value: 'label4'
        },
        {
          label: '金额(元)',
          value: 'label5'
        }
      ]
    }
  },

  created () {
    this.tableList = this.shuffleArray(this.tableList.map(item => {
      return {
        ...item,
        label4: item.label4.toFixed(2),
        label5: item.label5.toFixed(2)
      }
    }))
  },

  methods: {
    shuffleArray (array) {
      for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1))
        ;[array[i], array[j]] = [array[j], array[i]]
      }
      return array
    }
  }
}
</script>

<style lang="scss" scoped>
.realtime-data {
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>

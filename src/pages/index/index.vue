<template>
  <div>
    <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
      style="height:200px"
    >
    <block v-for="item in imgUrls" :key="item">
      <swiper-item>
        <image :src="item" style="width:100%;"/>
      </swiper-item>
    </block>
  </swiper>
  <i-grid i-class="no-border">
      <i-grid-item @click="goList(item.url)" i-class="no-border" v-for="item in grids" :key="item">
          <i-grid-icon>
              <image :src="item.img" />
          </i-grid-icon>
          <i-grid-label>{{item.type}}</i-grid-label>
      </i-grid-item>
  </i-grid>
  <i-panel title="强烈推荐">
    <view>
      <i-card @click="goType(item.type)" i-class="split" v-for="item in recommand" :key="item" :extra="item.name" :thumb="item.img">
          <view slot="content">推荐理由：{{item.remark}}</view>
          <view slot="footer">地址：{{item.address}}</view>
      </i-card>
    </view>
  </i-panel>
  </div>
</template>

<script>
import card from '@/components/card'
import top from '@/data/top.json'
export default {
  data () {
    return {
      imgUrls: [
        '/static/images/ba8049666749e8beaa00a5ebf8499731.jpg',
        '/static/images/848e230d5579b41a1ddde64a5977cdff.jpeg' 
       ],
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000,
      grids: [
        {type:'名胜古迹',img:'/static/images/1.png',"url":'../list/main?type=1'},
        {type:'美食',img:'/static/images/3.png',"url":'../list/main?type=2'},
        {type:'馆类景点',img:'/static/images/2.png',"url":'../list/main?type=3'},
        {type:'寺庙',img:'/static/images/4.png',"url":'../list/main?type=4'}
      
      ],
      recommand: top
    }
  },
  components: {
    card
  },
  methods: {
    goList (url) {
      mpvue.navigateTo({ url })
    },
    goType (type) {
      let url = '../list/main?type=' + type
      mpvue.navigateTo({ url })
    }
  },
  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
div >>> .split {
  margin-bottom: 10pt;
}
</style>
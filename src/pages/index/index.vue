<template>
  <div>
    <swiper 
        :indicator-dots="indicatorDots"
        :autoplay="autoplay"
        :interval="interval" 
        :duration="duration"
      >
        <block v-for="img in imgurls" :key="img">
          <swiper-item>
            <image :src="img" style="width=100%"/>
          </swiper-item>
        </block>
      </swiper>
    <i-grid i-class="no-border">
    <i-grid-item @click="gotype(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
    </i-grid>
    <i-panel :title="title_name">
     <view style="padding: 15px;">     
       <i-card v-for="item in top" :key="item" i-class="split" :title="item.name" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
         <view slot="content">{{item.remark}}</view>
         <view slot="footer">{{item.address}}</view>
        </i-card>    
     </view>
    </i-panel>
  </div>
  </template>

<script>
export default {
  data () {
    return {
      title_name: "热门",
      grids:[
        {title: "名胜古迹",image: "/static/images/1.png"},
        {title: "美食",image: "/static/images/3.png"},
        {title: "馆类景点",image: "/static/images/2.png"},
        {title: "寺庙",image: "/static/images/4.png"}
      ],
       top:[
        {name: "景点名称1",address: "地址",image: "https://i.loli.net/2017/08/21/599a521472424.jpg",remark: "介绍1"},
        {name: "景点名称1",address: "地址",image: "https://i.loli.net/2017/08/21/599a521472424.jpg",remark: "介绍2"},
        {name: "景点名称1",address: "地址",image: "https://i.loli.net/2017/08/21/599a521472424.jpg",remark: "介绍3"},
        {name: "景点名称1",address: "地址",image: "https://i.loli.net/2017/08/21/599a521472424.jpg",remark: "介绍4"}
      ],
      imgUrls: [
        'http://www.canyin88.com/uploads/image/2019/04/16/1555378220872933.jpg',
        'http://www.canyin88.com/uploads/image/2019/04/15/1555321255843942.jpg',
        'http://www.canyin88.com/uploads/190415/99ad8154e7332ca96ccb323580b3b8a2_3.jpg'
      ],
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000,
    }
  },

  methods: {
    gotype(){
      console.log(type)
      let url ='../list/main?type' +type.title
      mpvue.navigateTo({url})
    }
},

  created () {
   
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
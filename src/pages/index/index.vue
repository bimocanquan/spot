<template>
  <div>
    <i-grid i-class=no-border>
    <i-grid-item i-class=no-border>
        <i-grid-icon>
            <image src="/static/images/1.png" />
        </i-grid-icon>
        <i-grid-label>名胜古迹</i-grid-label>
    </i-grid-item>
     <i-grid-item i-class=no-border>
        <i-grid-icon>
            <image src="/static/images/3.png" />
        </i-grid-icon>
        <i-grid-label>美食</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class=no-border>
        <i-grid-icon>
            <image src="/static/images/2.png" />
        </i-grid-icon>
        <i-grid-label>馆类景点</i-grid-label>
    </i-grid-item>
     <i-grid-item i-class=no-border>
        <i-grid-icon>
            <image src="/static/images/4.png" />
        </i-grid-icon>
        <i-grid-label>寺庙</i-grid-label>
    </i-grid-item>
</i-grid>
<i-panel :title="title_name">
    <view style="padding: 15px;">
      <i-card i-class="split" title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
      <i-card i-class="split" title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
      <i-card i-class="split" title="卡片标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
      </i-card>
    </view>
</i-panel>
    </div>
</template>

<script>

export default {
  data () {
    return {
      title_name:"热门",
      grids:[
        {title:"经典文学",image:"/static/images/1.png"},
        {title:"推理悬疑",image:"/static/images/2.png"},
        {title:"都市言情",image:"/static/images/3.png"},
        {title:"外国著作",image:"/static/images/4.png"}
      ],
    }
  },

  methods: {
    
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

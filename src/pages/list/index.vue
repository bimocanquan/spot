<template>
  <div>
    <i-card v-for="item in list" :key="item" i-class="split" :title="item.name" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
         <view slot="content">{{item.remark}}</view>
         <view slot="footer">{{item.address}}</view>
        </i-card>   
    </div>
</template>

<script>

export default {
  data () {
    return {
      list:[]
    }
  },
onLoad (option){
    this.list = require('@/data/' + option.type + '.json')
    console.log(this.list)
},
  methods: {
    
    },

  created () {
   
  }
}
</script>

<style scoped>

</style>

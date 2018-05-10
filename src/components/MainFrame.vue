<template>
  <div id="Main">
    <div>
       <tab :line-width=2 active-color='#fc378c' v-model="index">
        <tab-item v-for="item in list2" 
                  :key="item.index" 
                  @on-item-click="tabclick(item.popular)">
                {{item.name}}</tab-item>
      </tab>

    <ArticalList  :popular="popular"></ArticalList>

    </div>
  </div>
</template>

<script>
import ArticalList from './ArticleList'
import {Tab,TabItem,Swiper,SwiperItem} from 'vux'

export default {
  components: {
    ArticalList,
    Tab,TabItem
  },
  directives:{
  },
  watch:{
  },
  mounted(){
  },
  data () {
    return {
      popular:true,
      index01: 0,
      list2:[{
        name:'熱門',
        popular:true,
        index:0
      },{
        name:'最新',
        popular:false,
        index:1
      }],
      demo2: '熱門',
      index: 0,
      getBarWidth: function (index) {
        return (index + 1) * 22 + 'px'
      }
    }
  },
  methods:{
    tabclick(p){
      this.popular = p
      console.log(this.popular)
    }
  }
}
</script>

<style>

</style>

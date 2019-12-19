<template>
  <div class='scroll' ref='scroll'>
    <ul>
      <li>160</li>
      <li>260</li>
      <li>360</li>
      <li>460</li>
      <li>560</li>
      <li>660</li>
      <li>760</li>
      <li>860</li>
      <li>960</li>
      <li>1060</li>
      <li>1160</li>
      <li>1260</li>
      <li>1360</li>
      <li>1460</li>
      <li>1560</li>
      <li>1660</li>
      <li>1760</li>
      <li>1860</li>
      <li>1960</li>
      <li>2060</li>
      <li>2160</li>
      <li>2260</li>
      <li>2360</li>
      <li>2460</li>
      <li>2560</li>
      <li>2660</li>
      <li>2760</li>
      <li>2860</li>
      <li>2960</li>
      <li>3060</li>
      <li>3160</li>
      <li>3260</li>
      <li>3360</li>
      <li>3460</li>
      <li>3560</li>
      <li>3660</li>
      <li>3760</li>
      <li>3860</li>
      <li>3960</li>
      <li>4060</li>
      <li>4160</li>
      <li>4260</li>
      <li>4360</li>
      <li>4460</li>
      <li>4560</li>
      <li>4660</li>
      <li>4760</li>
      <li>4860</li>
      <li>4960</li>
      <li>5060</li>
      <li>5160</li>
      <li>5260</li>
      <li>5360</li>
      <li>5460</li>
      <li>5560</li>
      <li>5660</li>
      <li>5760</li>
      <li>5860</li>
      <li>5960</li>
      <li>6060</li>
    </ul>
  </div>
</template>

<script>
export default {
  name:'Scroll',
  data(){
    return {
      scroll:{},
    }
  },
  mounted(){
    this.scroll = window.addEventListener('scroll',this.scrollHandle)
  },
  methods:{
    scrollHandle(e){
       
    }
  },

}
</script>

<style scoped>

</style>
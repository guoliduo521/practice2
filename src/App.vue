<template>
  <div id="app" ref='app'>
   <div class='head'>
     <input type="text" class='head1' value='0' v-model='num1' >
   </div>
   <div class='body' >
     <div class='body1'>
      <button value="1"  @click="onClick(1)" >1</button>
      <button value='2'  @click='onClick(2)' >2</button>
      <button  value='3'  @click='onClick(3)'>3</button>
      <button  value='+'  @click='onClick("+")' >+</button>
     </div>

      <div class='body1'>
      <button  value='4'  @click='onClick(4)' >4</button>
      <button  value='5'  @click='onClick(5)' >5</button>
      <button  value='6'  @click='onClick(6)' >6</button>
      <button value='-'  @click='onClick("-")'>-</button>
     </div>

      <div class='body1'>
      <button vlaue='7'  @click='onClick(7)' >7</button>
      <button  value='8'  @click='onClick(8)' >8</button>
      <button  value='9'  @click='onClick(9)' >9</button>
      <button  value='/'  @click='onClick("/")' >/</button>
     </div>

      <div class='body1'>
      <button vlaue='c' @click='onClick("c")'>c</button>
      <button value='0' @click='onClick(0)'>0</button>
      <button value='*' @click='onClick("*")'>*</button>
      <button value='=' @click='onClick("=")'>=</button>
     </div>
   </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  components: {
   
  },
 data(){
   return {
     num1:'',                   //input框双向绑定
     num2:'*',                  //记录每一次的输入内容           
     num4:false,                //连续输入符号会无法输入
   }
 },
  methods:{
    onClick(btn) {
      //当输入为number时
    if(typeof(btn) == 'number'){
       this.num1 +=btn
       this.num2 = btn
    }else if(btn != '=' && btn != 'c') {
      //输入为+-*/时，判断是否是两个符号相邻
     typeof(this.num2) === typeof(btn) ? this.num4 = false : this.num4 = true
     this.num2 = btn
     if(this.num1 !== null && this.num4 ){
       //num1里不为null值时，连个符号不相连时
      this.num1 +=btn
     } 
    }else {
     switch(btn){
       //当输入为删除和等号时；
       case 'c' :
         if(typeof(this.num1) == 'string'){
           //当num1为字符串时删除最后一个输入的字符
         this.num1 =this.num1.slice(0,this.num1.length-1) 
         }else {
           //计算出结果时，为number类型，删除键一下全部删除
           this.num1 = '';
         }
         break;
       case '=' :
        this.num1 = eval(this.num1)
     }
   }
  },
  }
}
</script>

<style scoped>
#app {
  height:500px;
  width:400px;
  background-color:pink;
}

.head {
  height:60px;
  width:300px;
  background-color: red;
  margin-top: 20px;
  position:relative;
  left:50px;
  top:30px;
  line-height:60px;
}

.body {
  position:relative;
  left:50px;
  top:50px;
  height:360px;
  width:300px;
  background-color: orange;
}

.body1 {
  display:flex;
}

.body1 button {
  height:60px;
  width:60px;
  flex:1;
  margin-left: 5px;
  margin-right: 5px;
  margin-top: 15px;
  margin-bottom:15px;
}

.head1 {
  width:300px;
  height:60px;
  font-size:26px;
}

</style>

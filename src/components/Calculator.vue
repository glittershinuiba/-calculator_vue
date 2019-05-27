<template>
  <div class="calculator_container">
    <div class="calculator_display">
      <div class="calculator_famul" v-cloak>{{ famul }}</div>
      <div class="calculator_result" v-cloak>{{ result }}</div>
    </div>

    <div class="calculator_body">
      <div class="calculator_1">
        <span class='calculator_item' @click="back()"> back </span>
        <span class="calculator_item" @click="clear_all()"> AC </span>
        <span class="calculator_item" @click="clear_result()"> C </span>
        <span class="calculator_item" @click="take_negative()"> ± </span>
        <span class="calculator_item" @click="square_root()"> √ </span>
        <span class="calculator_item" @click="pow()"> ^ </span>
        <span class="calculator_item" @click="jiecheng()"> x! </span>
      </div>
      <div class="calculator_2">
        <span class='calculator_item' @click="famulate(1)"> 1 </span>
        <span class="calculator_item" @click="famulate(2)"> 2 </span>
        <span class="calculator_item" @click="famulate(3)"> 3 </span>
        <span class="calculator_item" @click="famulate('+')"> + </span>
        <span class="calculator_item" @click="countdown()"> 1/x </span>
        <span class="calculator_item" @click="square()"> ^(2) </span>
        <span class="calculator_item" @click="sin()"> sin </span>
      </div>
      <div class="calculator_3">
        <span class='calculator_item' @click="famulate(4)"> 4 </span>
        <span class="calculator_item" @click="famulate(5)"> 5 </span>
        <span class="calculator_item" @click="famulate(6)"> 6 </span>
        <span class="calculator_item" @click="famulate('-')"> - </span>
        <span class="calculator_item" @click="famulate('(')"> ( </span>
        <span class="calculator_item" @click="famulate(')')"> ) </span>
        <span class="calculator_item" @click="cos()"> cos </span>
      </div>
      <div class="calculator_4">
        <span class='calculator_item' @click="famulate(7)"> 7 </span>
        <span class="calculator_item" @click="famulate(8)"> 8 </span>
        <span class="calculator_item" @click="famulate(9)"> 9 </span>
        <span class="calculator_item" @click="famulate('*')"> * </span>
        <span class="calculator_item" @click="famulate('π')"> π </span>
        <span class="calculator_item" @click="famulate('e')"> e </span>
        <span class="calculator_item" @click="tan()"> tan </span>
      </div>
      <div class="calculator_5">
        <span class='calculator_item' @click="percent()"> % </span>
        <span class="calculator_item" @click="famulate('0')"> 0 </span>
        <span class="calculator_item" @click="famulate('.')"> . </span>
        <span class="calculator_item" @click="famulate('/')"> / </span>
        <span class="calculator_item" @click="results()"> = </span>
       
        <span class="calculator_item" @click="log()"> log </span>
      </div>
      

    </div>
    
  </div>
</template>

<script>

export default {
  name: 'Calculator',
  data() {
    return{
      famul_res:"",
      famul:'',
      result:0
    }
  },
  methods:{
    famulate(e) {
      console.log("operate..");
      if(e=='π'){
         
        this.famul_res+='3.141';
        this.famul+='π';
        
      }
      
      else if(e=='e'){
        
        this.famul_res+='2.612';
        this.famul+='e';
        
      }
      else{
        this.famul= this.famul+e;
        this.famul_res+=e;
      }
      
    },
    results(){
      this.result= eval(this.famul_res);
    },
    back(){
      this.famul=this.famul.slice(0,-1);
      this.famul_res=this.famul.slice(0,-1);
    },
    clear_all(){
      this.famul='';
      this.famul_res='';
      this.result=0;
    },
    clear_result(){
      this.result=0;
    },
    jiecheng(){
      var result_1=eval(this.famul_res);
      for(var i=result_1-1;i>=1;i--){
        result_1=i*(result_1);
      }
      this.result=result_1;
      this.famul_res=this.result;
      this.famul='(' + this.famul+ ')!';
    },
    countdown(){
      this.result=1/eval(this.famul_res);
      this.famul='1/('+this.famul+')';
    },
    square(){
      this.result=eval(this.famul_res)*eval(this.famul_res);
      
    },
    percent(){
      this.famul='('+this.famul+')%';
      this.result=eval(this.famul_res)/100;
      this.famul_res=this.result;
    },
    sin(){
      this.famul="sin("+this.famul+")";
      this.result=Math.sin(eval(this.famul_res));
    },
    cos(){
      this.famul="cos("+this.famul+")";
      this.result=Math.cos(eval(this.famul_res));
    },
    tan(){
      this.famul="tan("+this.famul+")";
      this.result=Math.tan(eval(this.famul_res));
    },
    log(){
      this.famul="log("+this.famul+")";
      this.result=Math.log(eval(this.famul_res));
    },
    square_root(){
      this.famul='√('+this.famul+')';
      this.result=Math.sqrt(eval(this.famul_res));
      this.famul_res=this.result;
    },
    take_negative(){
      this.famul_res='-('+this.famul_res+')';
      this.famul='-('+this.famul+')';
      
    },
    pow(){
      
      this.famul=this.famul+'^';
      this.result=Math.pow(eval(this.famul_res),parseInt(this.famul_res[-1]));
      
      
    },


}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >


[v-cloak] {
  display: none;
  }
.calculator_display{
  padding: 5px;
  margin: 5px;
  border: 15px ;
  border-style: inset;
  border-color: rgb(124, 208, 230);
  max-width: 500px;
  margin: auto;
  height: 80px;
  margin-block-start: 5px;
}

.calculator_famul{
  padding: 5px;
  background-color: rgb(137, 144, 145);
  text-align: end;
  height: 40px;

}
.calculator_result{
  padding: 5px;
  background-color: rgb(137, 144, 145);
  text-align: end;
  
}
.calculator_1,.calculator_2,.calculator_3,.calculator_4,.calculator_5{
  border: 15px;
  border-color: rgb(124, 208, 230);
  max-width: 540px;
  margin: auto;
  display: flex;

  height: 70px;
  align-items: center;
  background-color: rgb(124, 208, 230);
}

span{
  background-color: rgb(137, 212, 231);
  width: 70px;
  margin:10px;
  text-align: center;
  line-height: 40px;
  font-size: 20px;
  box-shadow: 0.1rem 0.1rem 0.3rem rgb(18, 23, 24);
  cursor: pointer;
  border-radius: 0.5rem;
}
.calculator_5{
  margin-block-end: 15px;
}
.calculator_item:active {
  transform: translate(0.05rem,0.05rem);
  -moz-transform: translate(0.05rem,0.05rem);
  -webkit-transform: translate(0.05rem,0.05rem);
  border-radius: 0.5rem;
    
}

</style>

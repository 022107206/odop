<template>
  　　  <div id="app">
  　　    <div class="all">
  　　      <div class="one">
  　　        <div class="oneType" v-for="(item,index) in one" :key="index">
  　　          <b>{{one[index]}}</b>
  　　        </div>
  　　      </div>
  　　      <div class="twothreefour">
  　　        <div class="two">
  　　          <div class="twoType" v-for="(item,index) in two" :key="index" @mouseenter="open(index)">
  　　            <b>{{two[index]}}</b>
  　　          </div>
  　　        </div>
  　　        <div class="threefour" v-if="flag" @mouseleave="close()">
  　　          <div class="threefourType" v-for="(item,index) in three" :key="index">
  　　            <span class="three">{{three[index]}}</span>
  　　           <span class="four" v-for="(item4,index4) in four" :key="index4">
　　           {{four[index4]}}</span>
  　　          </div>
  　　        </div>
  　　      </div>
  　　    </div>
  　　  </div>
  　　</template>

<script>
  export default {
    name: 'app',
    data () {
      return {
        one:['一级类目','一级类目','一级类目','一级类目','一级类目'],
        two:['二级类目1','二级类目2','二级类目3','二级类目4','二级类目5'],
        three:[],
        four:['四级类目','四级类目','四级类目','四级类目','四级类目'],
        flag:false
      }
    },
    methods: {
      open(index){
        var index=index+1;
        var i=index+"";
        this.three=['三级目录'+i,'三级目录'+i,'三级目录'+i,'三级目录'+i,'三级目录'+i]
          this.flag=true
      },
      close(){
        this.flag=false
      }
    },
  }
</script>

<style>
　　*{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    }
　　.all{
    width: 80%;
    background:#eee;
    margin: 50px auto;
    display: -webkit-flex;
    display: flex;
    flex-wrap: wrap;
    }
　　.one{
    width: 100%;
    height: 50px;
    background: #FF8888;
    display: flex;
    display: -webkit-flex;
    flex-wrap: wrap;
    justify-content: space-around;
    }
　　.oneType{
    width: 20%;
    height: 50px;
    line-height: 50px;
    text-align: center;
    }
　　.oneType:hover{
    background-color:chocolate;
    color: #eee;
    }

    .twothreefour{
    width: 100%;
    height: 350px;
    background: #66FF66;
    display: -webkit-flex;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    }
　　.two{
    width: 15%;
    height: 100%;
    background: #77FFCC;
    display: -webkit-flex;
    display: flex;
    flex-direction: column;
    }
　　.twoType{
    width: 100%;
    height: 40px;
    line-height: 40px;
    text-align: center;
    background: #EEFFBB;
    }
　　.twoType:hover{
    background-color:black;
    color: #eee;
    }
　　.threefour{
    width: 40%;
    margin-right: 45%;
    height: 100%;
    background: #33FFDD;
    display: -webkit-flex;
    display: flex;
    flex-direction: column;
    }
　　.threefourType{
    margin: 10px auto;
    }
　　.three{
    font-family: 微软雅黑, 黑体;
    font-size: 16px;
    font-weight: 800;
    }
　　.four{
    font-family: 宋体;
    font-size: 12px;
    font-weight: 400;
    }
</style>

<template>
  <!-- html 짜는곳 -->

  <div class='black-bg' v-if="modalstate == true" >
  <div class="white-bg">
    <h4>상세페이지</h4>
    <p>상세페이지 내용.</p>
    <button @click="modalstate = false">닫기</button>
  </div>
  </div>

  <div class="menu">
    <!-- <a v-for="name in menu" : key="{{name}}">Home</a> -->
    <a v-for="(name, index) in menu" :key="index">{{ name }}</a>
    <!-- key에는 반복문에서 증가하는 index임 0,1,2,3,4,5,6 이렇게 증가함  -->
  </div>
  <div>
    <img src="./assets/room0.jpg" @click="modalstate = true">
    <h4>{{roomd[0].title}}</h4>
    <p>{{roomd[0].price}}</p>
    <button @click ="increase">신고 버튼</button> <span>{{count}}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg">
    <h4>{{ product[1] }}</h4>
    <p>{{ price2 }} 만원</p>
  </div>
  <div>
    <img src="./assets/room2.jpg">
    <h4>{{ product[2] }}</h4>
    <p>{{ price2 }} 만원</p>
  </div>
<div id="appp">
  <div>
    <h4>{{reverse}}</h4>
    <h4>{{price}}</h4>
    <input type ="number" v-model="price">
  </div>
</div>
</template>

<script>
// {{데이터 바인딩}}하는 이유 Html에 하드코딩해놓으면 나중에 변경 어려움. ex) 쇼핑몰 가격
// 이게 중요 실시간 랜더링을 위해서 vue는 데이터 바인딩된 값이 변경될 경우 알아서 재랜더링함 이게 중요!!!
// 메인페이지
// javascript 짜는 곳

// // document.getElementById().innerHTML = ?? 자바스크립트 방식
// function half() {
//   price1 = price1 / 2;
//   price2 = price2 / 2;
// }
import roomdata from './assets/roomdata.js';
export default {
  name: "App",
  data() {
    return {
      modalstate : false,
      price1: 1000,
      price2: 500,
      style1: "color:blue",
      product: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menu: ["Home,Products,randum"],
      count: 0,

    roomd : roomdata,
    };
  },
  methods: {
    increase(){
      this.count += 1; //this 써줘야함 methods 이 클래스에 있는 count라는 것을 알려주기 위해.ㄴ
    }

  },
  components: {

  },
  
};

</script>

<style>
/* css 짜는 곳  */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.menu {
  background: azure;
  padding: 15px;
  border-radius: 5px;
}

body{
  margin : 0px;

}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0,0.5,);
  position: fixed; padding:20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius:8px ;
  padding : 20px;
} 
</style>

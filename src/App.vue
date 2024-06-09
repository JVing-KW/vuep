<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <!-- html 짜는곳 -->

  <div class="menu">
    <a>Home</a>
    <a>products</a>
    <a>About</a>
  </div>
  <div>
    <h4>{{ product[0] }}</h4>
    <p>{{ price1 }}만원</p>
  </div>
  <div>
    <h4>{{ product[1] }}</h4>
    <p>{{ price2 }} 만원</p>
  </div>
  <div>
    <h4>{{ product[2] }}</h4>
    <p>{{ price2 }} 만원</p>
  </div>
  <button id="half_b" onClick="{">반값할인 버튼</button>
</template>

<script>
// {{데이터 바인딩}}하는 이유 Html에 하드코딩해놓으면 나중에 변경 어려움. ex) 쇼핑몰 가격
// 이게 중요 실시간 랜더링을 위해서 vue는 데이터 바인딩된 값이 변경될 경우 알아서 재랜더링함 이게 중요!!!
// 메인페이지
// javascript 짜는 곳
import HelloWorld from "./components/HelloWorld.vue";

// // document.getElementById().innerHTML = ?? 자바스크립트 방식
// function half() {
//   price1 = price1 / 2;
//   price2 = price2 / 2;
// }
export default {
  name: "App",
  data() {
    return {
      price1: 1000,
      price2: 500,
      style1: "color:blue",
      product: ["역삼동원룸", "천호동원룸", "마포구원룸"],
    };
  },
  components: {
    HelloWorld,
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
  background: darkblue;
  padding: 15px;
  border-radius: 5px;
} 
.menu a {
  color: white;
  padding: 10px;
}
</style>

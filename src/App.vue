<template>
  <div id="app">
    <div class="menu">
      <!-- 반복문 쓸 때 :key 안쓰면 에러남 -->
      <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
    </div>
    <!-- for문 이용하기
    <div v-for="(a, i) in products" :key="i">
      <h4>{{ a }}</h4>
      <p>50만원</p>
    </div> -->
    <div>
      <h4>{{ products[0] }}</h4>
      <p>50만원</p>
      <button v-on:click="increase1()">허위매물신고</button>
      <span>신고수 : {{ 신고수[0] }}</span>
    </div>
    <div>
      <h4>{{ products[1] }}</h4>
      <p>60만원</p>
      <button @click="increase2()">허위매물신고</button>
      <span>신고수 : {{ 신고수[1] }}</span>
    </div>
    <div>
      <h4>{{ products[2] }}</h4>
      <p>70만원</p>
      <button @click="increase3()">허위매물신고</button>
      <span>신고수 : {{ 신고수[2] }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  // 데이터 보관함
  data() {
    //여기에 데이터 보관, 데이터는 object 자료로 저장
    // {자료이름 : 자료내용}
    return {
      신고수: [0, 0, 0],
      메뉴들: ["Home", "Shop", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
    };
  },
  methods: {
    increase1() {
      this.$set(this.신고수, 0, this.신고수[0] + 1);
    },
    increase2() {
      this.$set(this.신고수, 1, this.신고수[1] + 1);
    },
    increase3() {
      this.$set(this.신고수, 2, this.신고수[2] + 1);
    },
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>

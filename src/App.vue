<template>
  <div class="menu">
    <a v-for="(a, i) in menu" :key="i">{{ a }}</a>
  </div>
  <Modal
    @modalClose="modalstatus = false"
    :oneroom="oneroom"
    :index="index"
    :modalstatus="modalstatus"
  ></Modal>
  <Card
    @modalOpen="
      modalstatus = true;
      index = $event;
    "
    v-for="(a, i) in oneroom"
    :key="i"
    :oneroom="oneroom[i]"
  ></Card>
  <disCount></disCount>
</template>

<script>
import data from "./assets/oneroom.js";
import disCount from "./DisCount.vue";
import Modal from "./Modal.vue";
import Card from "./Card.vue";

export default {
  name: "App",
  data() {
    return {
      index: 0,
      oneroom: data,
      modalstatus: false,
      menu: ["home", "products", "about"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      count: [0, 0, 0],
    };
  },
  methods: {
    increase(i) {
      this.count[i] += 1;
    },
  },
  components: {
    disCount: disCount,
    Modal: Modal,
    Card: Card,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.menu {
  background: darkblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: wheat;
  padding: 10px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
.disCount {
  background-color: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>

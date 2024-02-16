<template>
  <div class="black-bg" v-if="modalstatus == true">
    <div class="white-bg">
      <h4>{{ oneroom[index].title }}</h4>
      <img :src="oneroom[index].image" style="width: 100%" />
      <p>{{ oneroom[index].content }}</p>
      <input type="range" min="0" max="12" v-model="month" />
      <p>{{ month }}개월 선택함 {{ oneroom[index].price * month }}</p>
    </div>
    <disCount></disCount>
    <button @click="$emit('modalClose')">창 닫기</button>
  </div>
</template>
<script>
export default {
  name: "customModal",
  data() {
    return {
      month: 1,
    };
  },
  watch: {
    month(m) {
      if (m >= 13) {
        alert("13이상 입력하지마셈");
      } else if (isNaN(m) == true) {
        alert("문자열 입력하지마라");
        this.month = 1;
      }
    },
  },
  props: {
    oneroom: Object,
    index: Number,
    modalstatus: Boolean,
  },
};
</script>

<style></style>

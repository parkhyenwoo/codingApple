<template>
  <div class="black-bg" v-if="modalstatus == true">
    <div class="white-bg">
      <h4>{{ oneroom[index].title }}</h4>
      <img :src="oneroom[index].image" style="width: 100%" />
      <p>{{ oneroom[index].content }}</p>
      <p>{{ oneroom[index].price }}</p>
    </div>
    <disCount></disCount>
    <button @click="$emit('modalClose')">창 닫기</button>
  </div>
</template>
<script>
export default {
  name: "customModal",
  props: {
    oneroom: Object,
    index: Number,
    modalstatus: Boolean,
  },
};
</script>

<style></style>

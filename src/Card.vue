<template>
  <div>
    <img :src="oneroom.image" class="room-img" />
    <h4 @click="$emit('modalOpen', oneroom.id)">{{ oneroom.title }}</h4>
    <p>{{ oneroom.price }}만원</p>
  </div>
</template>
<script>
export default {
  name: "cardFor",
  props: {
    oneroom: Object,
  },
};
</script>

<style></style>

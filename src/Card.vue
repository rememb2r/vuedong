<template>
  <div @click="$emit('openModal', oneRoom.id)">
    <p>{{ oneRoom.id }}</p>
    <img class="oneroom-image" :src="oneRoom.image" />
    <h4 @click="$emit('openModal', oneRoom.id)">{{ oneRoom.title }}</h4>
    <h4>{{ oneRoom.price }}원</h4>
  </div>
</template>

<script>
  export default {
    name: "Card",
    props: {
    oneRoom: Object,
    indexClicked: Number,
    },
  };
</script>


<style>

</style>


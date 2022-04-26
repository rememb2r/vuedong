<template>
  <div class="black-bg" v-if="isModalOpened == true">
  <div class="white-bg" @click="$emit('closeModal')">
    <h2>{{ oneRoomDatas[indexClicked].title }}</h2>
    <img class="oneroom-modal-image" :src="oneRoomDatas[indexClicked].image"/>
  <h4>{{ oneRoomDatas[indexClicked].content }}</h4>
  <p>{{ oneRoomDatas[indexClicked].price }}</p>
  </div>
  </div>
</template>

<script>

  export default {
    name: "Modal",
    props: {
    oneRoomDatas: Array,
    isModalOpened: Boolean,
    indexClicked: Number,
    },

  };

</script>

<style>
</style>


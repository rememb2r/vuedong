<template>
  <div class="black-bg" v-if="isModalOpened == true">
    <div class="white-bg">
      <h2>{{ oneRoomDatas[indexClicked].title }}</h2>
      <img class="oneroom-modal-image" :src="oneRoomDatas[indexClicked].image"/>
      <h4>{{ oneRoomDatas[indexClicked].content }}</h4>
      <p>{{month}}개월 선택함 : {{ oneRoomDatas[indexClicked].price * (month > 1 && month < 99 ? month : 1) }}</p>
      <input v-model.number="month"/>
      <br><br>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>

  export default {
    name: "Modal",
    data() {
      return {
        month : 1,
      }
    },
    watch : {
      month(){

      },
    },
    props: {
      oneRoomDatas: Array,
      isModalOpened: Boolean,
      indexClicked: Number,
    },

  };

</script>

<style>
</style>


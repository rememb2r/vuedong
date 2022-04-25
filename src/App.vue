
<template>
  <Modal @closeModal="isModalOpened = false" :oneRoomDatas="oneRoomDatas" :isModalOpened="isModalOpened" :indexClicked="indexClicked"/>

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }} </a>
  </div>

  <Discount :discountPercent="discountPercent" />
  <Card @openModal="isModalOpened = true; indexClicked = $event;" v-for="(oneRoom, index) in oneRoomDatas"
   :key="oneRoom" :oneRoom="oneRoom" :indexClicked="index"/>
  
  <div>

  </div>

</template>


<script>

import oneRoomDataTemp from "./oneRoomData.js";
import DiscountBanner from "./DiscountBanner.vue";
import Modal from "./Modal.vue";
import Card from "./Card.vue";
export default {
  name: "App",
  data() {
    return {
    indexClicked: 0,
    oneRoomDatas: oneRoomDataTemp,
    isModalOpened: false,
    price1: 60,
    discountPercent: 30,
    menus: ["Home", "Shop", "About"],
    };
  },

  components: {
    Discount: DiscountBanner,
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
}

.oneroom-image {
  width: 80%;
  padding-top: 20px;
}

.oneroom-modal-image {
  width: 90%;
  padding-top: 10px;
}

body {
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
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}

</style>



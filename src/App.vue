<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <router-view /> -->
    <!-- <virtual-list :listData="data" :itemSize="100"></virtual-list> -->
    <virtual-list-update
      :listData="data"
      :estimatedItemSize="100"
      v-slot="slotProps"
    >
      <item :item="slotProps.item" />
    </virtual-list-update>
  </div>
</template>

<script>
import VirtualList from "./components/VirtualList.vue";
import VirtualListUpdate from "./components/VirtualListUpdate/VirtualListUpdate.vue";
import faker from "faker";
import Item from "./components/VirtualListUpdate/Item.vue";

let data = [];
for (let i = 0; i < 1000; i++) {
  data.push({
    i,
    value: faker.lorem.sentences() // mock长文本出来
  });
}

export default {
  components: { VirtualList, VirtualListUpdate, Item },
  name: "App",
  data() {
    return {
      data
    };
  }
};
</script>

<style>
html {
  height: 100%;
}
body {
  height: 100%;
  margin: 0;
  padding: 0;
}
#app {
  /* font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
  height: 100%;
}
</style>

<template>
  <div id="app">
    <h2>Draggable list</h2>
    <draggable group="words" :list="itemsList" @change="showDragged">
      <div
        class="np-item np-item-unselectable"
        v-for="item in itemsList"
        :key="item.id"
      >
        {{ item.name }}
      </div>
    </draggable>
    <div class="np-credits">wwww.nightprogrammer.com</div>
  </div>
</template>

<script>
import draggable from "vuedraggable";
import items from "./items";

export default {
  name: "App",
  components: {
    draggable,
  },
  data() {
    return {
      itemsList: items,
    };
  },
  methods: {
    showDragged(e) {
      console.log(e.moved);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  padding: 24px;
}

.np-credits {
  font-size: 12px;
  margin-top: 12px;
  color: #4b4b4b;
}

.np-item {
  padding: 4px;
  border: 1px solid #eee;
  border-radius: 4px;
  background: #eee;
  cursor: pointer;
  margin: 6px 0;
}

.np-item:active {
  background: rgb(168, 168, 168);
}

.np-item-unselectable {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
</style>
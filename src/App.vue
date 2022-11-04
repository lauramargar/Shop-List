<template>
  <!-- eslint-disable --> 
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1>SHOPPING LIST</h1>
    <div id="shop-wrap">
      <!-- (A) ADD NEW ITEM -->
      <div id="shop-form">
        <input type="text" id="shop-item" placeholder="Item Name" v-model="item" required/>
        <button type="submit" id="item-add" @click="addElement()">Add</button>
      </div>

      <!-- (B) SHOPPING LIST -->
      <div v-for="(item, index) in list" :key="item" class="item-row">
          <div class="item-name">{{item}}</div>
          <button id="item-del" @click="deleteElement(index)">Delete</button>
      </div>
    </div>
   <!-- eslint-disable --> 
</template>

<script lang="ts">
/* eslint-disable */
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  data: function () {
    return {
      list: ['patata','lechuga','manzanas'],
      item: '',
    }
  },
  methods: {
    addElement: function () {
      this.list.push(this.item);
    },
    deleteElement: function (index:number) {
      this.list.splice(index,1);
    }
  }
});
/* eslint-disable */
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
#shop-wrap, #shop-wrap > * { box-sizing: border-box; }
#shop-wrap input {
  padding: 10px;
  border: 0;
}
#item-add{
  cursor: pointer;
  background: #5a75d6;
  border: none;
  color: white;
  padding: 8px 25px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
}
#shop-form, .item-row {
  display: flex;
  align-items: center;
}
#shop-item, .item-name { flex-grow: 1; }

/* (B) WRAPPER */
#shop-wrap {
  max-width: 500px;
  padding: 15px;
  background: #f2f2f2;
  border: 2px solid #eee;
}

/* (C) SHOPPING LIST */
.item-row { margin-top: 10px; }
.item-name {
  padding: 5px;
  background: #fff;
}
.item-name.item-got { background: #f5fffa; }
.item-name.item-got:before {
  content: "\02713";
  margin-right: 5px;
  font-weight: bold;
  color: #00d036;
}
#item-del { 
  background: #df4343; 
  border: none;
  color: white;
  padding: 5px 25px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
}

/* [DOES NOT MATTER] */
* { font-family: arial, sans-serif; }
</style>

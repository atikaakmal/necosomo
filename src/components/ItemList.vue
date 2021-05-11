<template>
    <h1>Item list component</h1>
    <ul>
        <Item v-for="(item, index) in itemList" :key="item.id" :delMethod="del" :index="index" :item="item"/>
    </ul>

    <!-- add items in a list -->
    <input type="text" v-model="inputValue" id="addValue" class="form-control" />
    <button value="{{$id}}" @click="add()"   title="Add">add</button><br>
</template>

<script>
import lists from "./lists.json";
import Item from './Item.vue';
export default {
  name: 'ItemList',
  components: {
    Item
  },

    data() {
        return {
            itemList: lists
        };
    },
    methods: {
        add() {
            this.itemList.push({'id':(this.itemList.length) + 1,'name':this.inputValue});
            this.inputValue = '';
        },
        del(index) {
            this.itemList.splice(index, 1);
        }
    }
}
</script>

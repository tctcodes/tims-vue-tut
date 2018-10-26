<template>
  <v-layout align-center justify-start column>
    <!-- Todo Form -->
    <v-form>
      <v-text-field
        label="Add Todo Item"
        v-model="todoItem"
      ></v-text-field>
    </v-form>
    <!-- Add Item Button -->
    <v-btn @click="addItem">Add Item</v-btn>
    <!-- Todo List -->
    <v-list one-line>
      <template v-for="(item, index) in todoListItems">
        <v-list-tile
          :key="index"
        >
          <v-list-tile-content>
            <v-list-tile-title>{{ item }}</v-list-tile-title>
          </v-list-tile-content>
          <v-list-tile-action>
            <v-btn icon ripple @click="() => deleteItem(index)">
              <v-icon>delete</v-icon>
            </v-btn>
          </v-list-tile-action>
        </v-list-tile>
      </template>
    </v-list>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      todoItem: null,
      todoListItems: [
        'Make Tutorial',
        'Milk Cat',
        'Get Tacos',
        'Eat Tacos',
      ],
    };
  },
  methods:{
    deleteItem(atIndex) {
      this.todoListItems.splice(atIndex, 1);
    },
    addItem() {
      this.todoListItems = [this.todoItem, ...this.todoListItems];
    },
  },
};
</script>

<style>

</style>


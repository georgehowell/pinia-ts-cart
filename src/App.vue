<template>
  <div class="container">
    <Card>
      <h4>Add new item</h4>
      <!-- Create new item -->
      <AddItem />
    </Card>
    <Card>
      <h4>Your items ({{ cart.itemsCount }})</h4>
      <ItemsList />
    </Card>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useCartStore } from './store/cart';
import Card from '@/components/Card.vue';
import AddItem from '@/components/AddItem.vue';
import ItemsList from '@/components/ItemsList.vue';


export default defineComponent({
  name: 'App',
  components: { Card, AddItem, ItemsList },
  setup() {
    const cart = useCartStore()
    return { cart }
  }
});
</script>

<style>
#app {
  font-family: 'Open Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<script setup lang="ts"></script>
<template>
  <div>
    <h1>グループシャッフル</h1>
    <div>
      <h2>Group 1</h2>
      <ul>
        <li v-for="item in group1" :key="item.id">{{ item.name }}</li>
      </ul>
    </div>
    <div>
      <h2>Group 2</h2>
      <ul>
        <li v-for="item in group2" :key="item.id">{{ item.name }}</li>
      </ul>
      <button @click="shuffleItems">シャッフル</button>
    </div>
    <hr />
    <NuxtLink to="/">トップページへ</NuxtLink>
  </div>
</template>

<script>
import { shuffle } from '~/utils/js/shuffle.js';

export default {
  data() {
    return {
      items: [
        { id: 1, name: 'Item 1' },
        { id: 2, name: 'Item 2' },
        { id: 3, name: 'Item 3' },
        // Add more items as needed
      ],
      group1: [],
      group2: []
    };
  },
  mounted() {
    this.shuffleItems();
  },
  methods: {
    shuffleItems() {
      const shuffledItems = shuffle([...this.items]);

      // Split the shuffled array into two groups
      const halfway = Math.ceil(shuffledItems.length / 2);
      this.group1 = shuffledItems.slice(0, halfway);
      this.group2 = shuffledItems.slice(halfway);
    }
  }
};
</script>
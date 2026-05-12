<script setup>
import { ref } from 'vue'
import FoodCard from './components/FoodCard.vue'
const foods = ref([
  { name: '寿司', emoji: '🍣' },
  { name: 'ハンバーガー', emoji: '🍔' },
  { name: '丼', emoji: '🍚' },
  { name: 'オムライス', emoji: '🥚' },
  { name: 'イタリアン', emoji: '🍝' },
  { name: '中華料理', emoji: '🍜' },
  { name: 'とんかつ', emoji: '🐖' },
  { name: '韓国料理', emoji: '🫕' },
  { name: '鍋系', emoji: '🍲' },
  { name: '居酒屋', emoji: '🍶' },
  { name: 'ファミレス', emoji: '🍴' },
<<<<<<< HEAD
  { name: '豚骨ラーメン', emoji: '🐷🍜' }
=======
  { name: 'ラーメン', emoji: '🍜' },
  { name: 'ステーキ', emoji: '🍖' }
>>>>>>> 020347d (ステーキ追加)
])

const pickedFoodIndex = ref(0)
const newFoodIndex = ref(1)

function pickFood(index) {
  pickedFoodIndex.value = index
  newFoodIndex.value++
}
</script>

<template>
  <main>
    <h1 class="title">今日何食べる？</h1>
    <FoodCard
      :name="foods[pickedFoodIndex].name"
      :emoji="foods[pickedFoodIndex].emoji"
      @click="pickFood(pickedFoodIndex)"
    />
    <template v-if="newFoodIndex < foods.length">
      <p>VS</p>
      <FoodCard
        :name="foods[newFoodIndex].name"
        :emoji="foods[newFoodIndex].emoji"
        @click="pickFood(newFoodIndex)"
      />
    </template>
  </main>
</template>

<style scoped>
main {
  width: 350px;
  margin: 100px auto;
  text-align: center;
}
.title {
  margin-bottom: 60px;
}
</style>

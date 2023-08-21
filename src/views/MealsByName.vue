<template>
  <div class="p-8 pb-0">
    <input
      type="text"
      v-model="keyword"
      class="rounded border-2 border-gray-200 w-full"
      placeholder="Search for Meals"
      @change="searchMeals"
    />
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
    <div
      v-for="meal of meals"
      :key="meal.idMeal"
      class="bg-white shadow rounded-xl max-h-full"
    >
      <router-link to="/">
        <img
          :src="meal.strMealThumb"
          alt="strMeal"
          class="rounded-t-xl h-48 w-full object-cover"
      /></router-link>
      <div class="p-3">
        <h3 class="font-bold">{{ meal.strMeal }}</h3>
        <p class="mb-4">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Harum quod
        </p>
        <div class="flex items-center justify-between">
          <a
            :href="meal.strYoutube"
            target="_blank"
            class="px-2 py-1 rounded border-2 bg-red-400 border-red-500 hover:bg-red-600 transition-colors text-white"
            >Youtube</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed } from "@vue/reactivity";
import { onMounted, ref } from "vue";
import { useRoute } from "vue-router";
import store from "../store";

const route = useRoute();
const keyword = ref("");
const meals = computed(() => store.state.searchedMeals);

function searchMeals() {
  store.dispatch("searchMeals", keyword.value);
}

onMounted(() => {
  keyword.value = route.params.name;
  if (keyword.value) {
    searchMeals();
  }
});
</script>

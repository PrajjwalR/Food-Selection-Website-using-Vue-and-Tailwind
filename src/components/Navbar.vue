<template>
  <header class="bg-wheat shadow h-16 flex justify-between items-center">
    <router-link
      :to="{ name: 'home' }"
      class="inline-flex items-center h-full px-5"
      >Home</router-link
    >
    <div class="flex items-center gap-1 h-full">
      <router-link
        :to="{ name: 'byName' }"
        class="inline-flex items-center transition-colors px-2 h-full hover:bg-purple-100"
      >
        Search Meals
      </router-link>
      <router-link
        :to="{ name: 'byLetter' }"
        class="inline-flex items-center transition-colors px-2 h-full hover:bg-purple-100"
      >
        Meals by Letter
      </router-link>
      <router-link
        :to="{ name: 'ingredients' }"
        class="inline-flex items-center transition-colors px-2 h-full hover:bg-purple-100"
      >
        Meals by Ingredients
      </router-link>
    </div>
  </header>
</template>

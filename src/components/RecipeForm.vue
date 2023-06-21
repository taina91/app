<template lang="">
  <form @submit.prevent>
    <h4>Создание рецепта</h4>
    <input v-model="recipe.title" type="text" placeholder="Название" />
    <input v-model="recipe.author" type="text" placeholder="Автор" />
    <my-button @click="createRecipe">Создать</my-button>
  </form>
</template>
<script>
export default {
  data() {
    return {
      recipe: {
        title: "",
        author: "",
      },
    };
  },
  methods: {
    createRecipe() {
      this.recipe.id = Date.now();
      this.$emit("create", this.recipe);
      this.recipe = {
        title: "",
        author: "",
      };
    },
  },
};
</script>
<style lang=""></style>

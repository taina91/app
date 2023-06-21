<template lang="">
  <div>
    <navbar></navbar>
    <h1>Страница с рецептаит</h1>
    <my-select v-model="selectedSort" :options="sortOptions"> </my-select>
    <my-button @click="showDialog">Создать рецепт</my-button>
    <my-dialog v-model:show="dialogVisible">
      <recipe-form @create="createRecipe" />
    </my-dialog>
    <recipe-list :recipes="recipes" @remove="removeRecipe" />
  </div>
</template>
<script>
import RecipeForm from "@/components/RecipeForm";
import RecipeList from "@/components/RecipeList";
import axios from "axios";
export default {
  components: {
    RecipeForm,
    RecipeList,
  },
  data() {
    return {
      recipes: [
        // { id: 1, title: "Сырники", author: "кто-то" },
        // { id: 2, title: "Йогурт", author: "точно не я" },
        // { id: 3, title: "Кашка", author: "этот чел" },
      ],
      dialogVisible: false,
      selectedSort: "",
      sortOptions: [
        { value: "title", name: "По названию" },
        { value: "body", name: "По телу" },
      ],
    };
  },
  methods: {
    createRecipe(recipe) {
      this.recipes.push(recipe);
      this.dialogVisible = false;
    },
    removeRecipe(recipe) {
      this.recipes = this.recipes.filter((p) => p.id !== recipe.id);
    },
    showDialog() {
      this.dialogVisible = true;
    },
    async fetchRecipes() {
      try {
        const response = await axios.get(
          "https://jsonplaceholder.typicode.com/posts?_limit=10"
        );
        this.recipes = response.data;
      } catch (e) {
        alert("Error");
      }
    },
  },
  mounted() {
    this.fetchRecipes();
  },
};
</script>
<style lang="css">
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&family=Poppins:wght@400;600&family=Roboto:ital,wght@0,400;0,700;1,300&display=swap");
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Roboto", sans-serif;
}
html {
  background-color: #f5f5f7;
}
</style>

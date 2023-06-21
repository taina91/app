<template lang="">
  <div class="recipe">
    <div class="photo"></div>
    <div>
      <div class="title">{{ recipe.title }}</div>
      <div class="author">Автор: {{ recipe.author }}</div>
    </div>
    <div class="recipe__bths">
      <my-button @click="$emit('remove', recipe)">Удалить</my-button>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    recipe: {
      type: Object,
      required: true,
    },
  },
};
</script>
<style lang="css" scoped>
.recipe {
  border-radius: 0px 0px 100px 0px;
  background-color: #ffffff;
  width: 1032px;
  height: 261px;
  padding: 25px;
  margin: 25px;
  display: grid;
  grid-template-columns: 215px 3fr 1fr;
}
.photo {
  width: 215px;
  height: 211px;
  background-color: #dde8b9;
}
.title {
  font-weight: 700;
  font-size: 32px;
  color: #2b2c2e;
  margin-left: 24px;
}
.author {
  font-style: italic;
  font-weight: 300;
  font-size: 16px;
  color: #9f9db0;
  margin-top: 8px;
  margin-left: 24px;
}
.recipe__bths {
  justify-self: end;
}
</style>

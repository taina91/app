<template lang="">
  <nav>
    <img src="@/img/logo.svg" alt="" />
    <ul class="menu">
      <li class="menu__item">Рецепты</li>
      <li class="menu__item">Холодильник</li>
      <li class="menu__item">Избранное</li>
    </ul>
    <div class="btns">
      <my-button>Войти</my-button>
    </div>
  </nav>
</template>
<script>
export default {
  name: "navbar",
};
</script>
<style lang="css">
nav {
  display: grid;
  grid-template-columns: 151px 4fr 1fr;
  margin: 40px;
  align-items: center;
}
.menu {
  display: flex;
  justify-content: flex-start;
  justify-self: start;
  margin-left: 30px;
}
.menu__item {
  list-style-type: none;
  margin: 30px;
  color: #2b2c2e;

  font-weight: 400;
  font-size: 20px;
}
.btns {
  justify-self: end;
  display: flex;
}
</style>

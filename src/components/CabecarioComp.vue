<template>
  <header class="menu-superior">
    <div class="menu-esquerdo">
      <span> <RouterLink to="/">Home</RouterLink> </span>
      <span> | </span>
      <span> <RouterLink to="/livros">Livros</RouterLink> </span>
      <span> | </span>
      <span> <RouterLink to="/autores">Autores</RouterLink> </span>
      <span> | </span>
      <span> <RouterLink to="/editora">Editora</RouterLink> </span>
    </div>
  </header>
</template>

<style>
header span {
  padding: 0 20px;
}
.menu-superior {
  border-radius: 40px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>

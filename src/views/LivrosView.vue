<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      novo_livro: "",
      livros: [
        {
          id: "ac803529-5e2d-45b2-a907-ca993bb301ea",
          livro: "Harry Potter e a Pedra  Filosofal ",
          autor: "J.K Rowling",
        },
        {
          id: "f0532191-04bb-44fe-be8b-8449ce321169",
          livro: "A sombra do vento",
          autor: "Carlos Ruíz Zafón",
        },
        {
          id: "29eaba8d-a376-485e-9509-5dddd6587f0d",
          livro: "O caçador de pipas",
          autor: "Khaled Hosseini",
        },
        {
          id: "d7c068f0-928f-4858-9ae3-eadc32edb230",
          livro: "Anjo da escuridão",
          autor: "Sidney Sheldon",
        },
      ],
    };
  },
  methods: {
    salvar() {
      if (this.novo_livro !== "") {
        const novo_id = uuid();
        this.livros.push({
          id: novo_id,
          name: this.novo_livro,
        });
        this.novo_livro = "";
      }
    },
    excluir(livro) {
      const indice = this.livros.indexOf(livro);
      this.livros.splice(indice, 1);
    },
    alerta() {
      alert("ok");
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerencimento de Livros</h2>
    </div>
    <div class="form-input">
      <input
        type="text"
        v-model="novo_livro"
        @keyup.enter="salvar"
        placeholder="Livros"
      />
      <input
        type="text"
        v-model="novo_autor"
        @keyup.enter="salvar"
        placeholder="Autores"
      />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-items">
      <table>
        <thead>
          <tr>
            <td>ID</td>
            <td>Livros</td>
            <td>Autores</td>
            <td>Ações</td>
          </tr>
        </thead>
        <tbody>
          <tr v-for="livro in livros" :key="livro.id">
            <td>{{ livro.id }}</td>
            <td>{{ livro.name }}</td>
            <td>{{ livro.livro }}</td>
            <td>
              <button @click="alerta">Editar</button>
              <button @click="excluir">excluir</button>
            </td>
          </tr>
          <tr v-for="autor in autores" :key="autor.id">
            <td>{{ autor.id }}</td>
            <td>{{ autor.name }}</td>
            <td>{{ autor.autor }}</td>
            <td>
              <button @click="alerta">Editar</button>
              <button @click="excluir">excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style></style>

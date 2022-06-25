<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      novo_autor: "",
      autores: [
        {
          id: "ac803529-5e2d-45b2-a907-ca993bb301ea",
          autor: "J.K Rowling",
          livro: "Harry Potter e a Pedra  Filosofal",
        },
        {
          id: "f0532191-04bb-44fe-be8b-8449ce321169",
          autor: "Carlos Ruíz Zafón",
          livro: "A sombra do vento",
        },
        {
          id: "29eaba8d-a376-485e-9509-5dddd6587f0d",
          autor: "Khaled Hosseini",
          livro: "O caçador de pipas",
        },
        {
          id: "d7c068f0-928f-4858-9ae3-eadc32edb230",
          autor: "Sidney Sheldon",
          livro: "Anjo da escuridão",
        },
      ],
    };
  },
  methods: {
    salvar() {
      if (this.novo_autor !== "") {
        const novo_id = uuid();
        this.autores.push({
          id: novo_id,
          name: this.novo_autor,
        });
        this.novo_autor = "";
      }
    },
    excluir(autor) {
      const indice = this.autores.indexOf(autor);
      this.autores.splice(indice, 1);
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
      <h2>Gerencimento de Autores</h2>
    </div>
    <div class="form-input">
      <input type="text" placeholder="Livros" />
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
            <td>Autores</td>
            <td>Livros</td>
            <td>Ações</td>
          </tr>
        </thead>
        <tbody>
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

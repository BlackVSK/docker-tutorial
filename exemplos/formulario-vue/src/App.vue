<script setup>
import { reactive, ref } from 'vue'

const titulo = ref('Oi VueJs!')
const mostrarResultado = ref(false)

const categorias = [
  {
    id: 1,
    nome: 'Eletrônicos'
  },
  {
    id: 2,
    nome: 'Vestuário'
  },
  {
    id: 3,
    nome: 'Brinquedos'
  },
  {
    id: 4,
    nome: 'Móveis'
  },
  {
    id: 5,
    nome: 'Alimentos'
  },
  {
    id: 6,
    nome: 'Bebidas'
  },
  {
    id: 7,
    nome: 'Informática'
  },
  {
    id: 8,
    nome: 'Papelaria'
  }
]

const produto = reactive({
  nome: '',
  preco: 0,
  quantidade: 0,
  medida: '',
  categorias: []
})

function formatarPreco(preco) {
  return `R$ ${preco.toFixed(2).replace('.', ',')}`
}

function buscarNome(id) {
  return categorias.find(categoria => categoria.id === id).nome
}

</script>

<template>
  <h1>{{ titulo }}</h1>
  <div class="container">
    <div class="formulario">
      <h2>Formulário para cadastro do produto</h2>
      <div class="row">
        <label for="">Nome:</label>
        <input type="text" v-model="produto.nome" />
      </div>
      <div class="row">
        <label for="">Preço (em reais):</label>
        <input type="number" step="0.01" v-model="produto.preco" />
      </div>
      <div class="row">
        <label for="">Quantidade:</label>
        <input type="number" v-model="produto.quantidade" />
      </div>

      <fieldset>
        <legend>Unidade de medida</legend>
        <div class="items-radiobox">
          <input type="radio" value="unidade" v-model="produto.medida" /> Unidades
          <input type="radio" value="peso" v-model="produto.medida" /> Peso
        </div>
      </fieldset>
      <fieldset>
        <legend>Categorias</legend>
        <div class="items-checkbox">
          <template v-for="categoria in categorias" :key="categoria.id">
            <input type="checkbox" :value="categoria.id" v-model="produto.categorias" /> {{ categoria.nome }}
          </template>
        </div>
      </fieldset>
      <button @click="mostrarResultado = !mostrarResultado">Mostrar</button>
    </div>
    <div v-if="mostrarResultado" class="resultado">
      <h2>Dados do produto</h2>
      <p>Nome: {{ produto.nome }}</p>
      <p>Preço: {{ formatarPreco(produto.preco) }}</p>
      <p>Em estoque: {{ produto.quantidade }}</p>
      <p>Medida: {{ produto.medida }}</p>
      <p>Categorias: {{ produto.categorias }}</p>
      <h4>Categorias selecionadas:</h4>
      <p v-for="categoria_id in produto.categorias" :key="categoria_id">- {{ buscarNome(categoria_id) }}</p>
    </div>
  </div>
  <div class="altera-titulo">
    <h2>Informe um novo título: </h2>
    <input type="text" v-model="titulo" />
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: flex-start;
  gap: 2rem;
  margin-top: 1rem;
  padding: 0 2rem;
}

.formulario,
.resultado {
  width: 45vw;
  min-height: 70vh;
  border-radius: 20px;
  padding: 20px
}

.formulario {
  background-color: #d29696
}

.formulario .row {
  width: 80%;
  margin: 1.3rem 0;
  display: flex;
  justify-content: space-between;
}

.items-checkbox,
.items-radiobox {
  display: grid;
  grid-template-columns: auto 1fr;
  align-items: center;
}

.resultado {
  background-color: #98e0aa;
}

button {
  padding: .5rem 1rem;
  border: none;
  background-color: #f1f1f1;
  border-radius: 10px;
  cursor: pointer;
}

button:hover {
  background-color: #e1e1e1;
}

.altera-titulo {
  background-color: #98e0aa;
  margin: 1rem 2rem;
  border-radius: 20px;
  padding: .75rem;
  display: flex;
  gap: 1rem
}
</style>

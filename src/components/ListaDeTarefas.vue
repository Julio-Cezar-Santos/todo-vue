<script setup>
import { inject } from 'vue';

const estado = inject('estado');
const getTarefasFiltradas = inject('getTarefasFiltradas');
</script>

<template>
    <div class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in getTarefasFiltradas()">
            <input @change="evento => tarefa.finalizada = evento.target.checked" type="checkbox"
                :checked="tarefa.finalizada" :id="tarefa.titulo">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">{{ tarefa.titulo }}</label>
        </li>
    </div>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>
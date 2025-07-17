<script setup>
import { inject } from 'vue';

const estado = inject('estado');
const cadastrarTarefa = inject('cadastrarTarefa');
</script>

<template>
    <form @submit.prevent="cadastrarTarefa">
        <div class="row">
            <div class="col">
                <input :value="estado.tarefaTemp" @change="evento => estado.tarefaTemp = evento.target.value" required
                    type="text" class="form-control" placeholder="Digite aqui a descrição da tarefa">
            </div>
            <div class="col-md-2">
                <button type="submit" class="btn btn-primary">Cadastrar</button>
            </div>
            <div class="col-md-2">
                <select @change="evento => estado.filtro = evento.target.value" class="form-control">
                    <option value="todas">Todas</option>
                    <option value="pendentes">Pendentes</option>
                    <option value="finalizadas">Concluídas</option>
                </select>
            </div>
        </div>
    </form>
</template>
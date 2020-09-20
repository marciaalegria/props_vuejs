<template>
<div class="container fondo">
    <br>
    <br>
    <h3>{{ titulo }}</h3>
    <br>
    <span>Tarea</span> <input v-model="newTask" placeholder="Ingresar Nueva Tarea" required>
    <i style="font-size: 25px; color:purple" class="fas fa-plus-circle" v-on:click.enter="addNewTodo"></i>
    <p v-for="(task, index) in tasks">{{task}} <i class="fas fa-trash-alt" style="color:red" v-on:click.enter=" tasks.splice(index, 1)"></i></p>
</div>
</template>
<script>
export default {
    data() {
        return {
            newTask: '',
            tasks: [
                'pagar Netflix',
            ]
        }
    },
    props: {
        titulo: String,
        require: true
    },
    methods: {
        addNewTodo: function () {
            if (this.newTask == "") {
                alert("Agrega una tarea antes de añadir")
            } else {
                this.tasks.push(this.newTask)
                this.newTask = ''
            }
        },
    },
}
</script>
<style scoped>
.margen {
    margin-right: 5%;
}
span {
    font-weight: bold;
    font-size: 150%;
    border-left: 20px;
    margin-right: 3%;
}
.separar {
    margin-top: 2%;
}
.fondo {
    background-color:pink;
}
</style>
<template>
    <button @click="borrarTodos">Borrar toda la lista</button>
</template>

<script>
export default {
    name: 'delete-list',
    methods: {
        borrarTodos(){
            if ( confirm("Vas ha borrar todas las tareas")){
                this.$emit("delete-all")
            }
        }
      },
}
</script>
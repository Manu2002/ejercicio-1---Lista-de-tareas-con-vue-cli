<template>
    <form @submit.prevent="">
        <input v-model="newTarea">
        <button @click="addNuevo">Añadir</button>
    </form>
</template>

<script>
export default {
    name: 'add-list',
    props: ['todos'],
    data() {
            return { 
                newTarea: ''
            }
        },
    methods: {
        addNuevo(){
            alert('Quiero añadir')
              if(this.newTarea){
               this.$emit('add-new', {descrip: this.newTarea, done: false})
                this.newTarea = ' ';
            } 
        }
    }
}
</script>
<template>
    <ul>
        <TodoItem v-for="elem in todos" :key="elem.id" :elem="elem"></TodoItem>
    </ul>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
    name: 'list',
    props: ['todos'],
    methods:{
        delTodo(index){
            this.$emit('del-new', index);
        }
    },
    components: {
        TodoItem,
        
    }
}
</script>
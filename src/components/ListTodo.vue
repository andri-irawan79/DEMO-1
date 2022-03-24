<template>
    <div class="container-xl w-100 my-5">
        <table class="w-100 table-striped">
            <tr class="text-black">
                <th class="col-1">No.</th>
                <th class="col-7">Todo</th>
                <th class="col-4">Action</th> 
            </tr>
            <tr v-for="(todo, index) in todoList" :key="index">
                <TodoItems :todoList="todoList" :todo="todo" :index="index"/>   
            </tr>   
        </table>
    </div>
</template>

<script>
import TodoItems from '@/components/TodoItems.vue'

export default {
    name: 'ListTodo',
    components: {
        TodoItems,
    },
    props: {
        todos: Array,
    },
    data() {
        return {
            todoList: this.todos,
        };
    }
}
</script>



<style scoped>
th,
tr,
td {
    border: 1px solid rgb(168, 168, 168);
    padding: 10px;
}

table tr th {
    background-color: royalblue;
}

table tr:nth-child(odd) {
    background-color: rgb(231, 233, 238);
}

table tr:nth-child(odd) {
    background-color: rgb(231, 233, 238);
}
</style>


// methods: {
//         deletTodo(index) {
//             this.todoList.splice(index, 1);
//         },
//         doEdit(index){ 
//             this.isEdit = true;
//             this.editedTodo = this.todoList[index];
//         },
//         addEdit(index){
//             this.todoList.splice(index, 1, this.editedTodo);
//             this.isEdit = false;
//         },
//         changeButtonEdit() {
//             return this.isEdit ? 'Done' : 'Edit';
//         } 
//     }

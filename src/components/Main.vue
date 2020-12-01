<template>
<v-container class="mt-10">
    <v-layout row wrap class="justify-center align-content-center"> 
        <v-flex xs6>
            <ListAdd @listAdd="listAdd"/>
        </v-flex>
    </v-layout>
    <v-layout row wrap class="justify-center"> 
        <v-flex xs6 class="listdiv">
            <List :todoList="todoList" @deleteTodo="deleteTodo"/>
        </v-flex>
    </v-layout>
</v-container>
</template>

<script>
import List from './List';
import ListAdd from './ListAdd';

export default {
    components:{
        List,
        ListAdd
    },
    data() {
        return {
            todoList:[]
        }
    },
    methods: {
        listAdd(memo) {
            console.log('추가 에밋!');
            this.todoList.push(memo);
        },
        deleteTodo(id){
            this.todoList.splice(id,1);
        }
    },
}
</script>

<style scioed>
.listdiv {
    position: absolute;
    width: 40%;
}
</style>
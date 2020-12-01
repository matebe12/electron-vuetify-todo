<template>
  
      <v-layout row wrap> 
          <v-flex>
            <v-card v-for="(list, index) in todoList" :key="index"
                class="pb-5 pt-5 pl-5 pr-5 ma-5 cardDiv"  :id="`id${index}`" >
                    <div class="listline" @click="isToggle(index)">
                        <v-flex xs12 class="listcontent">
                    {{list}}
                        </v-flex>
                        
                    </div>
                    <div @click="deleteTodo(index)"  class="btnicon">
                            <v-icon left>{{ icons.mdiDelete }}</v-icon>
                    </div>
            </v-card>
          </v-flex>
      
      </v-layout>
</template>

<script>import {
    mdiAccount,
    mdiPencil,
    mdiShareVariant,
    mdiDelete,
  } from '@mdi/js'
export default {
    
props:['todoList'],
data() {
    return {
        icons:{
            mdiAccount,
        mdiPencil,
        mdiShareVariant,
        mdiDelete,
        }
    }
},
methods: {
    isToggle(id){
        let ids = document.getElementById(`id${id}`);
        console.log('토글');
        ids.classList.toggle('use');
    },
    deleteTodo(id){
        this.$emit('deleteTodo',id);
    }
},

}
</script>

<style scoped>
    .use{
        background-color: #eee !important;
    }
    .use div {
        
        text-decoration:line-through;
    }
    .listline {
        width: 90%;
        cursor:pointer;
    }
    .btnicon {
        cursor:pointer;
    }
    .cardDiv {
        display: flex;
        justify-content: space-between;
        align-items: center;
        
    }
    .listcontent {
        display: flex;
        justify-content: center;
    }
</style>
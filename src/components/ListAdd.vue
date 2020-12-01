<template>
      <v-layout row wrap class="justify-center"> 
        <v-flex xs6>
            <v-col
          cols="12"
          sm="6"
          md="12"
        >
          <v-text-field
            label="투두리스트"
            v-model="memo"
            outlined
          ></v-text-field>
        </v-col>
        </v-flex>
        <v-flex xs3>
            <v-col
          cols="12"
          sm="6"
          md="9"
        >
          
      
        <v-btn @click="listAdd" color="success" height="50px">리스트 추가</v-btn>
        </v-col>
        </v-flex>
      </v-layout>
</template>

<script>
export default {
    data() {
        return {
            memo:''
        }
    },
    methods: {
        
            listAdd() {
                console.log('리스트 추가');
                if(this.memo ===  ''){
                    alert('입력해주세요.');
                    return;
                }
                this.$emit('listAdd', this.memo);
            }
    },
}
</script>

<style>

</style>
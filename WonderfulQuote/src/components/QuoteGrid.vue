<template>
  <div class="row">
        <appQuote v-for="(Quote,index) in Quotes" :key="index"
         @click.native="deleteQuote(index)"> 
             {{Quote}}
        </appQuote>
  </div>
</template>

<script>

import vinod from './Quote.vue'

export default {
    props:['Quotes'],
    components:{
        'appQuote': vinod
    },

    methods:{
        deleteQuote(index){
          this.$emit('DeleteOps',index)
        }
    }
}
</script>

<style>

</style>
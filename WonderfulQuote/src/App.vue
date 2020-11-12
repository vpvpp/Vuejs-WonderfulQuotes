<template>
    <div class="container">
   
   <appNewQuote @quoteadded="RecivingQuote"> </appNewQuote>
   <br> 
   <appQuoteGrid :Quotes="Quotes" @DeleteOps="DelQuote"></appQuoteGrid>
    <div class="row">
        <div class="col-sm-12 text-center" >
            <div class="alert alert-info"> info: click on quote to delete it!!</div>
        </div>
    </div>
    </div>


</template>

<script>

import grid from './components/QuoteGrid.vue'
import newQuote from './components/NewQuote.vue'

    export default {
        data(){
            return{
                maxQuote:10,
                Quotes:[
                 'Just a quote to see something'
                ]
            }
        },
        components:{
            'appQuoteGrid': grid,
            'appNewQuote':newQuote
        },
        methods:{
            RecivingQuote(newincomingquote){
                this.Quotes.push(newincomingquote);
            },
            DelQuote(index){
                this.Quotes.splice(index,1);
            }
        }
    }
</script>

<style>

.lead{
    font-style: italic;

}
</style>

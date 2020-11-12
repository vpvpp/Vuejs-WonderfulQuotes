<template>
   <div>
  <appHeader :QuotesCount="Quotes.length" :MaxQuotes="MaxQuote"></appHeader>
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
    </div>


</template>

<script>

import grid from './components/QuoteGrid.vue'
import newQuote from './components/NewQuote.vue'
import header from './components/Header.vue'
    export default {
        data(){
            return{
                MaxQuote:10,
                Quotes:[
                 'Just a quote to see something'
                ]
            }
        },
        components:{
            'appQuoteGrid': grid,
            'appNewQuote':newQuote,
            'appHeader': header
        },
        methods:{
            RecivingQuote(newincomingquote){
                if(this.Quotes.length >= this.MaxQuote){
                    return alert('please delete some quotes first')
                }
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

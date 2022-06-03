<template>
    <div class="quote-list">
        <h3>All Quotes</h3>
        <div class="quote" 
            v-for="(quote,i) in quotes.slice().reverse()" :key="i">
            <div class="quote-header">
                {{this.quote.content}}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['quotes'],
    // created(){
    //     this.printQuote();
    // },
    // methods: {
        // printQuote(){
            // const data=await fetch('https://animechan.vercel.app/api/random').then(res=> res.json());
            // console.log(quotes);
            // if(this.quote.content){
            //     this.quotes=[...this.quotes,this.quote];
            // }
            // this.quote={
            //     content: data.quote,
            //     anime: data.anime,
            //     character: data.character
            // }
        // }
    // }

}
</script>

<style lang="scss" scoped>
.quote-list{
    padding: 2rem;
    max-width: 640px;
    margin: 0 auto;
    .quote{
        background-color: var(--light);
        color: var(--dark);
        padding: 1rem;
        border-radius: 1rem;
        margin-bottom: 1rem;

        &-header{
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            line-height: 1.2em;
            max-height: 1.2em;
        }
        &:hover{
            .quote-header{
                white-space: unset;
                max-height: unset;
            }
        }
    }
}
</style>
<template>
    <div class="app">
        <AppHeader title="The Anime Quotes"/>
        <AppQuote :quote="quote"/>
        <div class="button-container">
            <button @click="fetchQuote">Generate</button>
        </div>
        <!-- Error on displaying the list, it going to quotes variable but getting API is getting null content which is generating error -->
        <QuoteList :quotes="quotes" />
    </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppQuote from './components/AppQuote.vue';
import QuoteList from './components/QuoteList.vue';

export default {
    name: 'App',
    components: {
        AppHeader, AppQuote, QuoteList
    },
    data(){
        return {
            quote: {
                content: '',
                anime: '',
                character: ''
            },
            quotes: []
        }
    },
    // created(){
    //     this.fetchQuote();
    // },
    methods: {
        async fetchQuote(){
            const data=await fetch('https://animechan.vercel.app/api/random').then(res=> res.json());
            // console.log(data);
            console.log(this.quotes);
            if(this.quote.content){
                this.quotes=[...this.quotes,this.quote];
            }
            else this.quotes=[...this.quotes];
            this.quote={
                content: data.quote,
                anime: data.anime,
                character: data.character
            }
        }
    }
}
</script>

<style lang="scss">
:root{
    --primary: #D81E5B;
    --secondary: #8A4FFF;
    --tertiary: #32CbFF;
    --dark: #131A26;
    --light: #EEE;
    --grey: #848484;
}
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.button-container{
    display: flex;
    justify-content: center;
    margin: 4rem auto;
    button{
        padding: 1rem;
        border: transparent; outline: none;
        background-color: var(--dark);
        color: var(--light);
        border-radius: 1rem;
        font-size: 1.1rem;
        transition: 0.4s;
        cursor: pointer;
        &:hover{
            background-color: var(--tertiary);
            color: var(--dark);
        }
    }

}

</style>
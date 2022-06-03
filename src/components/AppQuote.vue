<template>
    <section class="quote">
        <div class="quote-content">{{quote.content}} </div>
        <div class="quote-info">
            <div class="quote-info-anime">{{quote.anime}}</div>
            <div class="quote-info-author">{{quote.character}}</div>
        </div>
    </section>
</template>

<script>
export default {
    props: ['quote'],
}
</script>

<style lang="scss" scoped>
    .quote{
        position: relative;
        margin: 0 auto;
        max-width: 768px; width: 70vw;
        &-content{
            position: relative;
            font-size: 1.5rem;
            font-weight: 500;
            background-color: var(--dark);
            color: var(--light);
            margin-top: 3rem;
            padding: 3rem;
            border-radius: 1.25rem;
            &:before, &:after{
                content: " ' ' ";
                color: var(--light);
                margin: 0px;
            }
        }
        &-info{
            position: absolute;
            left: 0; right: 0;
            top: 0; bottom: 0;  padding: 2rem;
            &-author,&-anime{
                position: absolute;
                padding: 1rem; font-size: 1.25rem;
                font-size: 400;
                border-radius: 10px;
                color: var(--light);
            }
            &-author{
                bottom: -2rem; right: -2rem;
                transform: translateY(-50%);
                background-color: var(--secondary); 
            }
            &-anime{ 
                left: -2rem; top: -2rem;
                background-color: var(--tertiary);
                color: var(--dark); 
            }
        }
    }
</style>
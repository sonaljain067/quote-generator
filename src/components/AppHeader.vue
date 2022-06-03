<template>
    <header>
        <h1>{{title}}</h1>
    </header>
</template>

<script>
export default {
    props: ['title']
}
</script>

<style lang="scss" scoped>
    header{
        padding: 2rem;
        display: flex;
        justify-content: center;
        h1{
            font-size: 2rem;
            color: var(--dark);
            font-weight: 700;
            text-transform: uppercase;
            padding-bottom: 0.5rem;
            border-bottom: 5px solid var(--primary);
        }
    }
</style>
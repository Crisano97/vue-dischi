<template>
        <div class="card">
            <img :src="poster" alt="">
            <h3>{{ title }}</h3>
            <span>{{ author }}</span>
            <span>{{ year }}</span>
        </div>        
</template>

<script>
export default {
    props: {
        'poster': String,
        'title': String,
        'author': String,
        'genre': String,
        'year': [Number, String],
    }
}
</script>

<style lang="scss" scoped>
    
    

    .card{
        display: flex;
        flex-direction: column;
        align-content: center;
        text-align: center;
        width: calc(100% / 5 - 1.5rem);
        // height: 15rem;
        padding: 1rem;
        gap: .7rem;
        margin-bottom: 1rem;
        background-color: #2E3A46;

        h3{
            text-transform: uppercase;
            color: white;
        }

        img{
            width: 100%;
        }

        span{
            color: gray;
        }
    }
</style>
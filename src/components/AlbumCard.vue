<template>
    <div class="albums-container">
        <div class="card">
            <img :src="poster" alt="">
            <span>{{ author }}</span>
            <span>{{ year }}</span>
        </div>
        
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
    
    .albums-container {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }

    .card{
        display: flex;
        flex-direction: column;
        align-content: center;
        width: calc(100% / 5 - .5rem);
        height: 15rem;
        background-color: aqua;
        padding: 1rem;
        gap: .7rem;
        margin-bottom: 1rem;

        img{
            width: 100%;
        }
    }
</style>
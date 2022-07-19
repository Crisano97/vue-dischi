<template>
    <div class="albums-container">
        <div class="card">
            <img src="https://img.discogs.com/vknPDdrqRbT92pNRX0W4I5N91jg=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-1246953-1448927086-6590.jpeg.jpg" alt="">
            <span>Bon JOvi</span>
            <span>1988</span>
        </div>
        
    </div>
</template>

<script>
export default {

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
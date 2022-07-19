<template>
        <div class="container">
            <AlbumCard />
        </div>
</template>

<script>

import AlbumCard from './AlbumCard.vue';

export default {
    components: {
        AlbumCard
    }
}
</script>

<style lang="scss" scoped>
    .container{
            width: 50%;
            margin: 0 auto;
            background-color: antiquewhite;
            
            
        }
</style>
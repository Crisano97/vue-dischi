<template>
    <main>
        <AlbumList />
    </main>
</template>

<script>

import AlbumList from './AlbumList.vue';

export default {
    components: {
        AlbumList
    }
}
</script>

<style lang="scss" scoped>
    main{
        height: 95vh;
        background-color: #1E2D3B;
        padding: 5rem 0;
    }
</style>
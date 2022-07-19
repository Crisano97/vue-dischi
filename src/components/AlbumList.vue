<template>
        <div class="container">
            <AlbumCard />
        </div>
</template>

<script>

import AlbumCard from './AlbumCard.vue';

export default {

    data: function(){
        return{

        }
    },
    name: 'AlbumList',
    components: {
        AlbumCard,
    },

    methods:{
        getAlbums(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                console.log(result);
            })
            .catch((error) => {
                console.warn(error);
            })
        }
    },
    
    created(){
        this.getAlbums();
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
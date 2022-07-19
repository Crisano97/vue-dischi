<template>
        <div class="container">
            <AlbumCard v-for="(album,index) in albums" :key="index" 
            :poster="album.poster"
            :title="album.title"
            :author="album.author"
            :genre="album.genre"
            :year="album.year"
            />
        </div>
</template>

<script>
import axios from 'axios'
import AlbumCard from './AlbumCard.vue';

export default {

    data: function(){
        return{
            albums : []
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
                this.albums = result.data.response;
                console.log(this.albums);
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
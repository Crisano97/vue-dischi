<template>
        <div class="container">
            <div class="select-container">
                <SelectGenre :list="albumGenre"/>
            </div>
            <div class="album-container">
                <AlbumCard
                v-for="(album,index) in albums" :key="index" 
                :poster="album.poster"
                :title="album.title"
                :author="album.author"
                :genre="album.genre"
                :year="album.year"
                />
            </div>
        </div>
</template>

<script>
import axios from 'axios';
import AlbumCard from './AlbumCard.vue';
import SelectGenre from './SelectGenre.vue';

export default {

    data: function(){
        return{
            albums : [],
            filteredAlbums: [],
            albumGenre: [],
        }
    },
    name: 'AlbumList',
    components: {
        AlbumCard,
        SelectGenre,
    },

    methods:{
        getAlbums(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                this.albums = result.data.response;
                console.log(this.albums);
                console.log(this.selectAlbumFilter('rock'))
                
                for (let i = 0; i < this.albums.length; i++){
                    if (!this.albumGenre.includes(this.albums[i].genre)){
                        this.albumGenre.push(this.albums[i].genre)
                    }
                }
                console.log(this.albumGenre);
            })
            .catch((error) => {
                console.warn(error);
            })
        },
        selectAlbumFilter(needle){
            const filteredAlbums = [...this.albums];
            console.log(filteredAlbums);
            return filteredAlbums.filter((album) => album.genre.toLowerCase().includes(needle))
        }
    },
    
    created(){
        this.getAlbums();
    }
}
</script>

<style lang="scss" scoped>
    .container{
        width: 60%;
        margin: 0 auto;
    }

    .select-container{
        padding: 2rem 0;
        text-align: end;
    }
    .album-container{
            
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }
</style>
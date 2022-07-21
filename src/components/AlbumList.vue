<template>
        <div class="container">
            <div class="select-container">
                <SelectGenre 
                @option="selectAlbumFromGenre"
                :albumGenreList="albumGenre"
                />
                <SelectAuthor 
                @authorOption="selectAlbumFromAuthor"
                :albumAuthorList="albumAuthor"
                />
            </div>
            <div class="album-container">
                <AlbumCard
                v-for="(album,index) in filteredAlbums" :key="index" 
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
import SelectAuthor from './SelectAuthor.vue';

export default {

    data: function(){
        return{
            albums : [],
            filteredAlbums: [],
            albumGenre: [],
            albumAuthor: [],
        }
    },
    name: 'AlbumList',
    components: {
        AlbumCard,
        SelectGenre,
        SelectAuthor
    },

    methods:{
        getAlbums(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) => {
                this.albums = result.data.response;
                this.filteredAlbums = this.albums;
                console.log(this.albums);
                
                for (let i = 0; i < this.albums.length; i++){
                    if (!this.albumGenre.includes(this.albums[i].genre)){
                        this.albumGenre.push(this.albums[i].genre);
                    }
                }
                
                for (let i = 0; i < this.albums.length; i++){
                    if (!this.albumAuthor.includes(this.albums[i].author)){
                        this.albumAuthor.push(this.albums[i].author);
                    }
                }

                console.log(this.albumGenre);
                console.warn(this.albumAuthor)
            })
            .catch((error) => {
                console.warn(error);
            })
        },
        selectAlbumFromGenre(needle){
            this.filteredAlbums = [...this.albums].filter((album) => album.genre.includes(needle));
            console.warn(this.filteredAlbums)
        },
        selectAlbumFromAuthor(needle){
            this.filteredAlbums = [...this.albums].filter((album) => album.author.includes(needle));
            console.warn(this.filteredAlbums)
        },
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
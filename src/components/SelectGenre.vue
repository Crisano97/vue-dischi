<template>
  <div>
    <select name="genre" id="genre-select" v-model="optionValue" @click="$emit('option', optionValue)">
        <option value="">Select a genre</option>
        <option :value="item" v-for="(item,index) in albumGenreList" :key="index">{{ item }}</option>
        
    </select>
  </div>
</template>

<script>
export default {
    data: function(){
        return{
            optionValue: '',
        }
    },
    props:{
        albumGenreList : Array
    },
    methods:{
        
    }
}
</script>

<style>

</style>
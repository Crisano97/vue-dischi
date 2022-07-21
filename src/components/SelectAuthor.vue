<template>
  <div>
    <select name="genre" id="genre-select" v-model="optionValue" @click="$emit('authorOption', optionValue)">
        <option value="">Select an author</option>
        <option :value="item" v-for="(item,index) in albumAuthorList" :key="index">{{ item }}</option>
        
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
        albumAuthorList : Array
    },
    methods:{
        
    }
}
</script>

<style>

</style>
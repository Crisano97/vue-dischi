<template>
  <div>
    <select name="genre" id="genre-select">
        <option value="">Select a genre</option>
        <option :value="item" v-for="(item,index) in list" :key="index">{{ item }}</option>
        
    </select>
  </div>
</template>

<script>
export default {
    data: function(){
        return{
            selectInput: ''
        }
    },
    props:{
        list : Array
    },
    methods:{
        
    }
}
</script>

<style>

</style>
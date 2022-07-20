<template>
  <div>
    <select name="genre" id="genre-select" v-model="optionValue" @click="$emit('option', optionValue)">
        <option value="">Select a genre</option>
        <option :value="item" v-for="(item,index) in list" :key="index">{{ item }}</option>
        
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
        list : Array
    },
    methods:{
        
    }
}
</script>

<style>

</style>
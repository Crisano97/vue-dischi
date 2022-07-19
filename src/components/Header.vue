<template>
  <header>
        <img src="../assets/logo-small.svg" alt="Spotify logo">
  </header>
</template>

<script>
import Header from '../../../vue-dc-comics/src/components/Header.vue'
export default {
  components: { Header },

}
</script>

<style lang="scss" scoped>
    header{
        // height: 5vh;
        padding: 1rem;
        background-color: #2E3A46;

        img{
            width: 2.5rem;
        }
    }
</style>
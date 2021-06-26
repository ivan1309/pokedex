<template>
  <div class="searchbar  flex justify-center">
    <form @submit.prevent="setPokemonUrl">
      <input type="text" v-model="searchvalue" class=" mt-10 p-2 border-blue-500 border-2" placeholder="Inserta pokemon">
    </form>
    <i class="fas fa-search" @click="setPokemonUrl" ></i>
  </div>
</template>

<script>
  export default {
    props: [
      'apiUrl'
    ],
    data: () => {
      return {
        searchvalue: '',
      }
    },
    methods: {
      setPokemonUrl() {
        if(this.searchvalue !== '')
          this.$emit('setPokemonUrl', this.apiUrl + this.searchvalue);
      }
    }
  }
</script>
<template>
    <div>
      <SearchBar @search="search" />
      <div
       v-if="arrResponse"
        class="row row-cols-5 g-4"
      >
        <CardCharacter
          v-for="response in arrResponse"
          :key="response"
          :img-url="response.poster"
          :title="response.title"
          :author="response.author"
          :year="response.year"
        />
      </div>
      
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  import CardCharacter from '@/components/CardCharacter.vue';
  import SearchBar from '@/components/SearchBar.vue';
  export default {
    name: 'PageMain',
    components: {
      CardCharacter,
      SearchBar,
    },
    data() {
      return {
        arrResponse: null,
        urlApi: 'https://flynn.boolean.careers/exercises/api/array/music',
        searchString: '', 
      };
    },
    computed: { 
    arrFiltered() {
      if (this.arrResponse) {
        return this.arrResponse.filter(
          (objResponse) => objResponse.name.trim().toLowerCase().includes(this.searchString.trim().toLowerCase()),
        );
      }
      return null;
    },
  },
    created() {
      
      axios.get(this.urlApi)
        .then((axiosResponse) => {
          console.log(axiosResponse);
          this.arrResponse = axiosResponse.data.response;
        });
    },
    methods: {
    search(searchString) {
      this.searchString = searchString; 
      this.$emit('search', searchString);
      axios.get(this.urlApi, {
         params: {
          name: searchString,
         },
       })
         .then((axiosResponse) => {
           console.log(axiosResponse);
           this.arrResponse = axiosResponse.data.result;
         });
    },
  },
  };
  </script>
  
  <style lang="scss" scoped>
  </style>
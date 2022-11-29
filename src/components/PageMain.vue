<template>
    <div>
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
  export default {
    name: 'PageMain',
    components: {
      CardCharacter,
    },
    data() {
      return {
        arrResponse: null,
        urlApi: 'https://flynn.boolean.careers/exercises/api/array/music', // TODO: pagination
      };
    },
    created() {
      // scaricare i dati
      axios.get(this.urlApi)
        .then((axiosResponse) => {
          console.log(axiosResponse);
          this.arrResponse = axiosResponse.data.response;
        });
    },
  };
  </script>
  
  <style lang="scss" scoped>
  </style>
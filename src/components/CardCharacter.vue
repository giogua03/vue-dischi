<template>
    <div class="col">
      <div class="contents text-center">
        <img
          :src="imgUrl"
          :alt="name"
          
        >
        <h2 class="title">
          {{ title }}
        </h2>
        <div class="autore">
          {{ author }}
        </div>
        <div class="anno">
          {{ year }}
        </div>
      </div>
    </div>
  </template>
  
  <script>
  
  export default {
    name: 'CardCharacter',
    props: {
      imgUrl: String,
      name: String,
      origin: String,
      species: String,
    },
  };
  </script>
  
  <style lang="scss" scoped>
  </style>
<template>
    <div class="col">
      <div class="contents text-center gimt">
        <img
          :src="imgUrl"
          :alt="title"
          class="img-fluid "
        >
        <h2 class="title">
          {{ title }}
        </h2>
        <div class="author">
          {{ author }}
        </div>
        <div class="year">
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
      title: String,
      author: String,
      year: String,
    },
  };
  </script>
  
  <style lang="scss" scoped>
  .gimt{
    border: 3px solid violet
  }
  </style>
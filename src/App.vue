<template>
  <div class="container">
    <PageHeader :results-for="searchString"/>
    <PageMain @search="search"/>
    
  </div>
</template>

<script>
import PageHeader from '@/components/PageHeader.vue';
import PageMain from '@/components/PageMain.vue';

export default {
  components: {
    PageHeader,
    PageMain,
    
  },

data() {
    return {
      searchString: '',
    };
  },
  methods: {
    search(data) {
      this.searchString = data;
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import url('https://fonts.googleapis.com/css2?family=Lato&display=swap');
*{
  background-color: grey;
}
</style>
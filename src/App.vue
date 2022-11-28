<template>
  <div class="container">
    <PageHeader />
    <PageMain />
    <PageFooter />
  </div>
</template>

<script>
import PageHeader from '@/components/PageHeader.vue';
import PageMain from '@/components/PageMain.vue';
import PageFooter from '@/components/PageFooter.vue';
export default {
  components: {
    PageHeader,
    PageMain,
    PageFooter,
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import url('https://fonts.googleapis.com/css2?family=Lato&display=swap');
</style>
<template>
  <section class="container">
    <paginate :data="data" :count-per-page="countPerPage" @change="paginate_data=$event"></paginate>
  </section>
</template>

<style lang="scss" scoped>
</style>

<script>
import Paginate from '../src/vue-mg-paginate'
import 'bootstrap/dist/css/bootstrap.min.css'
export default {
  data() {
    return {
      data: [],
      paginate_data: [],
      countPerPage: 10,
    }
  },
  mounted: function () {
    for(let i = 0; i < 101; i++) {
      this.data.push({
        id: i+1,
      })
    }
  },
  methods: {
    ///
  },
  components: {
    Paginate,
  },  
}
</script>
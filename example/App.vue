<template>
  <section class="container my-3">
    <paginate :data="data" :count-per-page="countPerPage" @change="paginate_data=$event" :current-page.sync="page"></paginate>
    <input type="text" class="form-control" v-model="page">
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
      page: 1,
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
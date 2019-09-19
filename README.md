# vue-mg-paginate
vue-mg-paginate

![npm](https://img.shields.io/npm/v/vue-mg-paginate)
![npm](https://img.shields.io/npm/dm/vue-mg-paginate)

## Installation

```
npm i vue-mg-paginate
```

## Usage

app.js

```javascript
import MgPaginate from 'vue-mg-paginate'
Vue.component('MgPaginate', MgPaginate)
```

Example:

```html
<template>
  <section class="container">
    <mg-paginate :data="data" :count-per-page="countPerPage" @change="paginate_data=$event"></mg-paginate>
  </section>
</template>

<style lang="scss" scoped>
</style>

<script>
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
    //
  },  
}
</script>
```

## License

MIT
<template>
    <vuejs-paginate
        v-model="page"
        :page-count="pageCount"
        :prev-text="prevText"
        :next-text="nextText"
        :container-class="'pagination'"
        :page-class="'page-item'"
        :page-link-class="'page-link'"
        :prev-class="'page-item'"
        :next-class="'page-item'"
        :prev-link-class="'page-link'"
        :next-link-class="'page-link'"
        :click-handler="clickCallback"
    >
    </vuejs-paginate>
</template>

<script>
import VuejsPaginate from 'vuejs-paginate'
export default {
    props: {
        data: {
            default: [],
        },
        countPerPage: {
            default: 20,
        },
        prevText: {
            default: '<span>&laquo;</span>',
        },
        nextText: {
            default: '<span>&raquo;</span>',
        },
    },
    data () {
        return {
            page: 1,
        }
    },
    mounted: function () {
        // console.log(this.value)
    },
    watch: {
        data: function () {
            this.clickCallback(1)
        }
    },
    computed: {
        pageCount: function () {
            const count = parseInt(this.data.length / this.countPerPage)
            if (this.data.length > count * this.countPerPage) return count + 1
            return count
        },
    },
    methods: {
        clickCallback: function(pageNum) {
            this.page = pageNum
            let list = this.data.concat()
            if (this.page) {
                list = list.splice((this.page - 1) * this.countPerPage, this.countPerPage)
            }
            this.$emit('change', list)
        }
    },
    components: {
        VuejsPaginate,
    }
}
</script>
<template lang='pug'>
  v-main
    v-container
      v-row.padded
        h1 Search
        v-spacer
        v-btn.btn.btn-primary(color='primary' @click='showSearch = true') Search
          span(v-if='searchResults') Again
      hr
      v-col
        v-row
          p(v-if='searchResults') {{searchResults.length}} results found matching "{{searchString}}":
          p(v-else) Pending Search Criterion...
        p &nbsp;
        hr
        p {{searchResults}}

    // Search Function ...
    v-dialog(v-model='showSearch')
      v-card
        v-card-title
          span Search for stuff
          v-spacer
          v-btn(small @click='showSearch = false')
            v-icon mdi-close
        v-card-text
          v-text-field(label='Search String' v-model='searchString' variant='outlined' prepend-icon='mdi-magnify')
            template(v-slot:append)
              v-btn.btn.btn-primary(color='primary' small :disabled='!searchString' @click='searchNow') Find
</template>

<script>

export default {
  name: 'Search',
  components: {
  },
  data () {
    return {
      searchString: '',
      showSearch: false,
      searchResults: null
    }
  },
  methods: {
    openSearch () {
      this.showSearch = true
    },
    searchNow () {
      console.log('search for ' + this.searchString)
      this.searchResults = []
    }
  }
}
</script>

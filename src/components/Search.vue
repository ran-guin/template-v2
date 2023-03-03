<template lang='pug'>

  v-btn(disable='!searchFor') Go
  v-btn(@click='showSearch = true') Search
  v-dialog(v-model='showSearch')

</template>

<script>
export default {
  name: 'Test',

  data: () => ({
    return {
      showSearh: false
    }
  }),
  props: {
    searchFor: { type: String }
  }
}
</script>

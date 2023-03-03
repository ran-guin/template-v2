<template lang='pug'>
  v-app
    v-app-bar(app)
      //- div.d-flex.align-center
      b.myLogo Logo

      v-spacer

      v-tabs(v-model='tab' align-tabs='center')
        v-tab(v-for='tab in tabs')
          router-link.myTab(:to='tab.link || tab.name')
            v-icon(v-if='tab.icon' @click='clickMe(tab)') {{tab.icon}}
            span(v-else @click='clickMe(tab)') {{tab.name}}

      v-spacer

      b.myMenu Menu

    v-main
      router-view

</template>

<script>

export default {
  name: 'App',

  data: () => ({
    tab: '',
    tabs: [
      { name: 'Home', icon: 'mdi-home' },
      { name: 'Test', onClick: 'customMethod' },
      { name: 'About' },
      { name: 'Search', icon: 'mdi-magnify' }
    ]
  }),
  methods: {
    clickMe (el) {
      if (el.onClick && this[el.onClick]) {
        console.log('click on element...' + el)
        this[el.onClick]()
      } else {
        console.log('no onclick method..')
      }
    },
    customMethod () {
      console.log('run custom method')
    }
  }
}
</script>

<style scoped>
  .myLogo {
    padding-right: 4rem;
  }
  .myMenu {
    padding-left: 4rem;
  }
  .myTab {
    text-decoration: none;
  }
  v-icon {
    color: red;
  }
</style>

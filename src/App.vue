<template lang='pug'>
  v-app
    v-app-bar(app height='120px')
      //- style='position: sticky'
      //- div.d-flex.align-center
      Logo.myLogo

      v-spacer

      v-tabs(v-model='tab' align-tabs='end')
        v-tab(v-for='tab in tabs')
          router-link.myTab(:to='tab.link || tab.name')
            v-icon(v-if='tab.icon' @click='clickMe(tab)') {{tab.icon}}
            span(v-else @click='clickMe(tab)') {{tab.name}}

      Menu()

    v-main
      router-view

</template>

<script>

import Logo from '@/components/CosineLogo'
import Menu from '@/components/Menu'

export default {

  name: 'App',
  components: {
    Logo,
    Menu
  },
  data: () => ({
    tab: '',
    tabs: [
      { name: 'Home' }, //, icon: 'mdi-home'
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
    padding-right: 0rem;
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

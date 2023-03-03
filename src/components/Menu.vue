<template lang='pug'>
  v-menu(v-model='mainMenu' width='290px' :close-on-content-click="false" bottom transition="scale-transition" offset-y)
    v-btn Open
    template(v-slot:activator='{on}')
      //- br
      //- b(v-for='item in items') {{item.name}}
      v-btn(@click='menuOpen = true')
        v-icon mdi-bars
    v-dialog(v-model='menuOpen')
</template>

<script>
export default {
  name: 'Test',

  data: () => ({
    mainMenu: false,
    menuOpen: false,
    items: [
      { name: 'Home' },
      { name: 'Test' },
      { name: 'About' }
    ]
  })
}
</script>

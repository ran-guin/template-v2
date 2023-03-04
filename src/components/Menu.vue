<template lang='pug'>
  .text-center
    //- v-menu()
    //-   template(v-slot:activator="{ props }")
    //-     v-btn(color="primary", v-bind="props") Dropdown
    //-   v-list
    //-     v-list-item(v-for="(item, index) in items", :key="index")
    //-       v-list-item-title Item {{ item.name }}
    //- v-btn#mainMenuBtn()
    v-btn#mainMenuBtn(color='primary')
      v-icon(color='white') mdi-menu
    v-menu(activator='#mainMenuBtn')
      //- template(v-slot:activator="{ props }")
      v-card
        v-list
          h3(align='center') Public
          v-divider
          v-list-item(v-for='item,index in items' :key='index' :value='index')
            v-list-item-title
              //- a.menuLink(v-if='item.link' :href='item.link') {{item.name}}
              router-link.menuLink(v-if='item.link' :to='item.link') {{item.name}}
              span(v-else) {{item.name}}
      //- v-icon mdi-bars
</template>

<script>
export default {
  name: 'Test',

  data: () => ({
    mainMenu: false,
    menuOpen: false,
    items: [
      { name: 'Home', link: 'Home' },
      { name: 'Test', link: 'Test' },
      { name: 'About', link: 'About' },
      { name: 'Personal Information that is over there' }
    ]
  })
}
</script>
<style scoped>
  .menuLink {
    text-decoration: none;
  }
</style>

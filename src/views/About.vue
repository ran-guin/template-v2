<template lang='pug'>
  v-main
    v-container
      h1 About Us
      hr
      p {{description}}
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Test',
  components: {
  },
  data: () => ({
    description: 'Fill in as required...'
  })
}
</script>

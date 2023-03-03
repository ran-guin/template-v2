<template lang='pug'>
  v-main
    v-container
      TestElement
</template>

<script>
import TestElement from '@/components/Test.vue'

export default {
  name: 'Test',
  components: {
    TestElement
  }
}
</script>

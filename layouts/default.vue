<template>
  <div>
    <Header />
    <ColorModePicker />

    <div class="min-h-screen" style="">
      <nuxt />
    </div>

    <Footer />
  </div>
</template>

<script>
import Header from '~/components/general/Header.vue'
import ColorModePicker from '~/components/general/ColorModePicker.vue'
import Footer from '~/components/general/Footer'

export default {
  components: {
    Header,
    ColorModePicker,
    Footer
  }
}
</script>

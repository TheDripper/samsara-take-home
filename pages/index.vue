<template>
  <main id="browse">
    <div class="bg-white accordion_container">
    </div>
  </main>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style lang="scss" scoped>
main {
  max-width: 100%;
  overflow: hidden;
}
#browse {
  @apply flex flex-col justify-end items-center;
  min-height: calc(100vh - 110px);
  
}
.accordion_container {
  height: 400px;
  max-width: 1400px;
  @apply relative w-full;
  &:before {
    background: white;
    content: '';
    position: absolute;
    top: 0px;
    left: 0px;
    transform: rotate(-20deg) translateY(-5%);
    width: 200vw;
    height: 200vw;
  }
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

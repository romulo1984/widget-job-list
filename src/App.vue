<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <img src="./assets/logo.png">
          <StyleGuide></StyleGuide>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import StyleGuide from './components/StyleGuide'

export default {
  name: 'app',
  components: {
    StyleGuide
  }
}
</script>

<style src="assets/less/app.less" lang="less"></style>

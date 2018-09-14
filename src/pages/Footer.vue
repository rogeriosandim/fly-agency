<template>
  <footer class="footer">
     © 2018 - All rights reserved. Site designed by <a href="https://github.com/rogeriosandim" >Fly - Agência Digital</a>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  props: {
    footer: String
  }
  
}
</script>

<style lang="scss">
$footer-padding: 2px;

.footer {
  text-align: center;
  margin-top: 20px;
  width: 100%;
  padding: $footer-padding;
  background-color: black;
  color: white;
}
</style>


<template>
  <footer class="footer">
     © 2018 - All rights reserved. Site designed by <a href="https://github.com/rogeriosandim" ><i class="fab fa-github"></i> Fly - Agência Digital</a>
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

.footer {
  text-align: center;
  margin-top: 20px;
  width: 100%;
  padding: 2px;
  background-color: black;
  color: white;
}
</style>


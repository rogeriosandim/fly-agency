<template>
  <div :class="{'headroom--unpinned': scrolled}"  v-on="handleScroll" class="headroom header">
    <div class="logo">
      <img alt="Fly Logo" src="http://placekitten.com/80/80">
    </div>
    <div class="nav">

    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    handleScroll() {
      if (this.lastPosition < window.scrollY && this.limitPosition < window.scrollY) {
        this.scrolled = true;
      } 
      if (this.lastPosition > window.scrollY) {
        this.scrolled = false;
      }
      this.lastPosition = window.scrollY;
    }
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  }
}
</script>

<style scoped>
  .header {
    width: 100%;
    background-color: #555;
    position: fixed;
  }
  .headroom {
    will-change: transform;
    transition: transform 200ms linear;
  }
  .headroom--pinned {
    transform: translateY(0%);
  }
  .headroom--unpinned {
    transform: translateY(-100%);
  }
  .logo {
    display: flex;
  }

</style>

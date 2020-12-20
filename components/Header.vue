<template>
  <header class="header">
    <nav class="nav"><Logo /></nav>
  </header>
</template>

<script>
export default {};
</script>

<style scoped>
.header {
  /* background: blue; */
}
.nav {
  padding: 100px;
  padding-right: 0;
}

@media only screen and (max-width: 600px) {
  .nav {
    padding: 10px;
  }
}
</style>
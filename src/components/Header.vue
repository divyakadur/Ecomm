<template>
  <!--Double navigation-->
  <header>
    <nav class="nav">
      <ul class="nav-links">
        <button class="link" id="home">
          <router-link to="/">DECATHLON</router-link>
        </button>
      </ul>
    </nav>
    <slot></slot>
  </header>
  <!--/.Double navigation-->
</template>

<script>
export default {
  name: 'Header'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: white;
  font-family: sans-serif;
  font-weight: bold;
  font-size: 2em;
   
}
#home{
 background-color: #008CBA;
 color: black
}
/* Only for snippet */
.double-nav .breadcrumb-dn {
  color: #fff;
}
</style>

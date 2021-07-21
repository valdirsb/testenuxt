<template>
  <div>
    <h1 class="text-center">Menu</h1>
    <div class="container">
      <div class="table-responsive">
      <table class="table">
        <tr>
          <td>
            <NuxtLink to="/page1">Pagina 1</NuxtLink>
          </td>
          <td>
            <NuxtLink to="/page2">Pagina 2</NuxtLink>
          </td>
          <td>
            <NuxtLink to="/page3">Pagina 3</NuxtLink>
          </td>
        </tr>
      </table>
    </div>
    </div>
    

    <nav>
      
      
      
    </nav>
    <Nuxt />
  </div>
</template>

<script>
export default {
  data () {
    return {
      produto: 'produto1'
    }
  }
}
</script>

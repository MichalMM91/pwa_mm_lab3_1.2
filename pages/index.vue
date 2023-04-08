<template>
  <div>
    <TopNav />
    <div class="quotes">
      <h2 class="padding50"><i>Witaj na witrynie naszego wyimaginowanego sklepu.<br>
        Odmierzaj swój bezcenny czas jednym z zegarków z naszej oferty</i></h2>
      <h3 class="padding50"><i>Wszystkie zdjęcia naszych produktów zostały stworzone przez sztuczną inteligencję</i></h3>
      <p class="padding50 fontSmall">CEO Świat zegarków - Piotr Kukułka</p>
    </div>
  </div>
</template>

<script>
import TopNav from '../components/nav/TopNav.vue';
export default {
  name: 'IndexPage',
  components: {TopNav},
  data() {
    return {

    }
  

  }
}
</script>

<style scoped>
  .quotes{
    width: 100%;
    height: 60vh;
    text-align: center;
  }
</style>
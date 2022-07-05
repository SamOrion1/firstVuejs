<template>
  <div>
    <h1>Beers Page List</h1>
    <br />
    <BeersList></BeersList>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import BeersList from '@/components/BeersList.vue';
undefined // @ is an alias to /src

@Options({
  components: {
    BeersList,
  },
})
export default class BeersView extends Vue {}
</script>
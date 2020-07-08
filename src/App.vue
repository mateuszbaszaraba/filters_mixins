<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3 col-lg-6 offset-lg-3 mt-5">
        <h1>Filters & Mixins</h1>
        <p>{{ text | toUppercase | to-lowercase }}</p>
        <hr>
        <input v-model="filterText" />
        <ul>
          <li v-for="fruit in filteredFruits" :key="fruit">{{ fruit }}</li>
        </ul>
        <hr>
        <app-list></app-list>
      </div>
    </div>
  </div>
</template>

<script>
  import list from './List';
  import { fruitMixin } from './fruitMixin';

export default {
  data () {
    return {
      text: 'Hola senorita!',
    }
  },
  filters: {
    toUppercase(value) {
      return value.toUpperCase()
    }
  },
  components: {
    appList: list
  },
  mixins: [fruitMixin]
}
</script>

<style>
</style>

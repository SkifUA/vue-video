<template>
  <div>
    <SearchBar v-on:termChange="onTermChange"></SearchBar>
    Hi!
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';

export default {
  name: 'App',
  components: {
    SearchBar
},
  methods: {
    onTermChange(searchTerm) {
      console.log(searchTerm);
    }
  }
}
</script>

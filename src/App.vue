<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
    Hi!
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
const API_KEY = 'AIzaSyChALGHb6aFHUjBo2I7qArOF4kWW9MlrhA';

export default {
  name: 'App',
  components: {
    SearchBar
},
  methods: {
    onTermChange(searchTerm) {
      axios
          .get('https://www.googleapis.com/youtube/v3/search', {
            params: {
              key: API_KEY,
              type: 'video',
              part: 'snippet',
              q: searchTerm
            }
          })
          .then(response => console.log(response));
    }
  }
}
</script>

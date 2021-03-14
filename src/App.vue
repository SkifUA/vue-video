<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList></VideoList>
    {{ videos.length }}
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from "./components/VideoList";

const API_KEY = 'AIzaSyChALGHb6aFHUjBo2I7qArOF4kWW9MlrhA';

export default {
  name: 'App',
  components: {
    VideoList,
    SearchBar
  },
  data() {
    return {
      videos: []
    };
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
          .then(response => {
            this.videos = response.data.items
          });
    }
  }
}
</script>

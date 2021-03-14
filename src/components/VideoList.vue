<template>
  <ul>
    VideoList
    {{ videos.length }}
  </ul>
</template>

<script>
import VideoListItem from "./VideoListItem";

export default {
  name: 'VideoList',
  comments: {
    VideoListItem
  },
  props: {
    videos: Array
  }
}
</script>

<style>

</style>
<template>
  <div id="app">
    <h1>LikeBar Test</h1>
    <LikeBar :likes="likes" :dislikes="dislikes"/>
  </div>
</template>

<script lang="ts">
import LikeBar from './components/LikeBar.vue';
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
    LikeBar,
  },
})
export default class App extends Vue {
  likes = 75;
  dislikes = 25;
}
</script>

<style>

</style>

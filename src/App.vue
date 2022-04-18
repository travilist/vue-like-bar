<template>
  <div id="app">
    <h1>LikeBar Test</h1>
    <p>{{likes}} likes | {{dislikes}} dislikes</p>
    <button @click="likes += 1">Like</button>
    <button @click="dislikes += 1">Dislike</button>
    <button @click="likes = 1; dislikes = 1">Reset</button>

    <LikeBar :likes="likes" :dislikes="dislikes" :key="likes+dislikes"/>
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
  likes = 1;
  dislikes = 1;
}
</script>

<style>
  #likebar {
    margin-top: 10px;
  }
  
  button {
    margin-right: 10px;
  }
</style>

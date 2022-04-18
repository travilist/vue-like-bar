<template>
    <div id="likebar">
        <span id="likes"/>
        <span id="dislikes"/>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class LikeBar extends Vue {
  @Prop() likes!: number;
  @Prop() dislikes!: number;

  total = 0;
  likesPct = 0;
  dislikesPct= 0;

  created(): void {
      console.log(`Creating likebar with ${this.likes} likes and ${this.dislikes} dislikes`);
      this.calculate();
  }
  
  beforeUpdate(): void {
      this.calculate();
  }

  calculate(): void {
      this.total = this.likes + this.dislikes;
      this.likesPct = this.likes / this.total;
      this.dislikesPct = this.dislikes / this.total;
      console.log(`Likes(Pct)\tDislikes(Pct)\n${this.likes}(${this.likesPct})\t${this.dislikes}(${this.dislikesPct})`);
  }
}
</script>

<style scoped>

</style>
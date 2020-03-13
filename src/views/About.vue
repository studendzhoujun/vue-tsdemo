<template>
  <div class="about">
    <p>{{msgg}}</p>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
@Component
export default class App extends Vue {
  private msgg: string = 'this is a about page';
}
</script>

<style lang="scss">
.about {
  background:#090;
  font-size:30px;
}
</style>

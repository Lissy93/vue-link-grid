<template>
  <section>
    <header>
        <h2>{{ tileSectionTitle }}</h2>
        <span> {{ tileSectionSubTitle }} </span>
    </header>
    <div>
        
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class TileSection extends Vue {
  @Prop() private tileSectionTitle!: string;
  @Prop() private tileSectionSubTitle?: string;
}
</script>

<style scoped lang="scss">

</style>

<template>
  <section>
    <header>
        <h2>{{ tileSectionTitle }}</h2>
        <span> {{ tileSectionSubTitle }} </span>
    </header>
    <div>
        <Tile 
            v-for="tile in this.tiles" 
            :key="tile.id"
            :name="tile.name"
            :description="tile.description"
            :url="tile.url"
            :icon="tile.icon"
        />
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import Tile from './Tile.vue';
Vue.component('Tile', Tile);


@Component
export default class TileSection extends Vue {
    @Prop() private tileSectionTitle!: string;
    @Prop() private tileSectionSubTitle?: string;
    @Prop() private tiles?: object;
}
</script>

<style scoped lang="scss">

</style>

<template>
  <section :style="sectionStyles" :class="`${theme}-theme tile-section`">
    <header class="tile-section-header">
        <h2 class="tile-section-title" :v-if="tileSectionTitle">{{ tileSectionTitle }}</h2>
        <span class="tile-section-sub-title" :v-if="tileSectionSubTitle"> {{ tileSectionSubTitle }} </span>
    </header>
    <div class="tile-wraper">
        <Tile
            v-for="tile in this.tiles" 
            :key="tile.id"
            :name="tile.name"
            :description="tile.description"
            :url="tile.url"
            :icon="tile.icon"
            :theme="theme"
        />
    </div>
  </section>
</template>

<script lang="ts">

    import { Component, Prop, Vue } from 'vue-property-decorator';
    import Tile from './Tile.vue';
    Vue.component('Tile', Tile);

    const defaultStyles = {};

    @Component
    export default class TileSection extends Vue {
        @Prop() private tileSectionTitle!: string;
        @Prop() private tileSectionSubTitle?: string;
        @Prop() private tiles?: object;
        @Prop() private theme?: string;
        @Prop() private styles?: object;

        private data() {
            return {
                sectionStyles: {
                    ...defaultStyles,
                    ...this.styles,
                },
            };
        }
    }
</script>

<style scoped lang="scss" type="text/scss">

    /* Default styles */
    .tile-section{
        padding: 1em;
        .tile-section-header{
            margin: 1em;
        }
        .tile-wraper{
            display: flex;
            flex-wrap: wrap;
        }
    }
</style>

<style src="../styles/index.scss" lang="scss" />




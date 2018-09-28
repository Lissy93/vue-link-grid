<template>
  <section :style="sectionStyles" :class="`${theme}-section-theme`">
    <header class="tile-section-header">
        <h2 :v-if="tileSectionTitle">{{ tileSectionTitle }}</h2>
        <span :v-if="tileSectionSubTitle"> {{ tileSectionSubTitle }} </span>
    </header>
    <div class="tile-wraper">
        <Tile
            class="tile-outer"
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
    .tile-wraper{
        display: flex;
        flex-wrap: wrap;
        .tile-outer {
            flex: 1;
        }
    }

</style>

<style src="../styles/index.scss" lang="scss" />




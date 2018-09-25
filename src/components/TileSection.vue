<template>
  <section :style="sectionStyles" :class="'theme-'+theme">
    <header>
        <h2 :v-if="tileSectionTitle">{{ tileSectionTitle }}</h2>
        <span :v-if="tileSectionSubTitle"> {{ tileSectionSubTitle }} </span>
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

<style scoped lang="scss">

    /* Default styles */

    /* Import all the individual theme sets */
    @import url('../styles/material-theme.scss');
    @import url('../styles/material-dark-theme.scss');

</style>




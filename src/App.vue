
<template>
  <div id="app">
    <TileSection 
      v-for="(section, sectionIndex) in this.sections"
      :key="sectionIndex" 
      :tileSectionTitle="section.sectionTitle" 
      :tileSectionSubTitle="section.sectionSubTitle" 
      :tiles = "section.tiles"
    />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import TileSection from './components/TileSection.vue';

@Component({
  data: () => {
    return  {
    sections: [
      {
        sectionTitle: 'Title',
        sectionSubTitle: 'SubTitle',
        tiles: [
        {
          id: 0,
          name: 'tile1',
          description: 'description of first tile',
          url: 'https://google.com',
          icon: 'https://via.placeholder.com/100x100',
        },
        {
          id: 1,
          name: 'tile TWO',
          description: 'description of first tile',
          url: 'https://google.com',
          icon: 'https://via.placeholder.com/100x100',
        },
        {
          id: 2,
          name: 'tile three',
          description: 'description of first tile',
          url: 'https://google.com',
          icon: '',
          },
        ],
      },
    ],
  };
  },
  components: {
    TileSection,
  },
})
export default class App extends Vue {}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

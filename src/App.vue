
<template>
  <div id="app">
    <TileSection 
      v-for="(section, sectionIndex) in this.sections"
      :key="sectionIndex" 
      :tileSectionTitle="section.sectionTitle" 
      :tileSectionSubTitle="section.sectionSubTitle"
      :styles="myStyle"
      :tiles = "section.tiles"
      theme="default"
    />
  </div>
</template>

<script lang="ts">

  import { Component, Vue } from 'vue-property-decorator';
  import TileSection from './components/TileSection.vue';

  import * as exampleData1 from './demo/example-tile-data1.json';

  @Component({
    data: () => {
      return  {
        myStyle: {},
        sections: exampleData1.default.sections,
      };
    },
    components: {
      TileSection,
    },
  })
  export default class App extends Vue {}
</script>


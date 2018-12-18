<template>


    <router-link 
        v-if="path" tag="div" :to="path"
        class="tile" v-bind:style= "[color ? {'background': color} : {}]"    
    >
        <img v-if="icon" :src="icon" alt="Icon" class="tile-icon">
        <div class="tile-texts">
            <span class="tile-name">{{ name }}</span>
            <span class="tile-description">{{ description }}</span>
        </div>
    </router-link>

    <a 
        v-else-if="url" :href="url" target="_blank" title="name"
        class="tile" v-bind:style= "[color ? {'background': color} : {}]"
    >
        <img v-if="icon" :src="icon" alt="Icon" class="tile-icon">
        <div class="tile-texts">
            <span class="tile-name">{{ name }}</span>
            <span class="tile-description">{{ description }}</span>
        </div>

    </a>

    <div v-else class="tile" v-bind:style= "[color ? {'background': color} : {}]">
        <img v-if="icon" :src="icon" alt="Icon" class="tile-icon">
        <div class="tile-texts">
            <span class="tile-name">{{ name }}</span>
            <span class="tile-description">{{ description }}</span>
        </div>
    </div>

</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Tile extends Vue {

    @Prop() private id!: number;
    @Prop() private name!: string;
    @Prop() private color?: string;
    @Prop() private description?: string;
    @Prop() private url?: string; // For anchor element only
    @Prop() private path?: string; // For router-link only
    @Prop() private icon?: string;
    @Prop() private theme?: string;

}

</script>

<style scoped lang="scss">
.tile{
    display: flex;
    align-items: center;
    text-decoration: none;
    margin: 1em;
    
    .tile-texts{
        width: 100%;
        padding: 1em;
        .tile-name{
            font-size: 1.2em;
        }
        .tile-description{
            font-size: 1em;
        }
    }
    span, img {
        display: block;
        text-align: center;
    }
}

</style>



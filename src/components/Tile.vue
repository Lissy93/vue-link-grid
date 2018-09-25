<template>
    <a :href="url" target="_blank"> 
        <span>{{ name }}</span>
        <img v-if="icon" :src="icon" alt="Icon">
    </a>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Tile extends Vue {

    @Prop() private id!: number;
    @Prop() private name!: string;
    @Prop() private description?: string;
    @Prop() private url?: string;
    @Prop() private icon?: string;
}

</script>

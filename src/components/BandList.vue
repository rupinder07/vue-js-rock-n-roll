<template>
    <div>
        <input type="text" placeholder="Add Band" v-model='bandName' @click="addBand" @keyup.enter="addBand">
        <ul>
            <BandItem v-for="band in bands" :key="band.name" v-bind:band="band">
            </BandItem>
        </ul>
    </div>
</template>

<script>
import BandItem from './BandItem.vue'

export default {
    name: 'BandList',
    data() {
        return {
            bandName: '',
            bands: [
                {
                    id: 1,
                    name: 'Beetles',
                    songs: [
                        "one", "two"
                    ]
                },
                {
                    id: 2,
                    name: 'Cold Play',
                    songs: [
                        "three", "four"
                    ]
                    
                }
            ]
        }
    },
    components: {
        BandItem
    },
    methods: {
        addBand(){
            this.bands.push({id:3, name: this.bandName, songs: []})
        }
    }
}
</script>

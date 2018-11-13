<template>
    <div>
        <li @click="toggle">
            {{band.id}} {{band.name}}
            <p v-show="open">
                {{band.songs | join}}
                <input type="text" placeholder="Add more songs" @click.stop @keyup.enter="addSong" v-model='newSong'/>
            </p>


        </li>
    </div>    
</template>

<script>
import BandItem from './BandItem.vue'

export default {
    name: 'BandItem',
    data(){
        return {
            newSong: '',
            open: false,
        }
    },
    props: {
        band: Object
    },
    filters: {
        join(arr) {
            return arr.join(', ')
        }
    },
    methods: {
        toggle() {
            this.open = !this.open;
        },
        addSong() {
            this.band.songs.push(this.newSong);
        }
    }
}
</script>

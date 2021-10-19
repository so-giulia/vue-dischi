<template>
    <div class="col-4 text-align-right">
        <label for="select">Filter by genre</label>
        <select name="genres" id="genres" class="rounded-pill" v-model="filter" @change="emitGenre">
            <option value="All">All</option>
            <option v-for="(genre, index) in genres" :key="index" :value="genre">
                {{genre}}
            </option>
        </select>
    </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
    name:'Filters',
    data(){
        return{
            genres:[],
            filter:''
        }
    },
    mounted(){
        eventBus.$on('selectGenre', albums =>{
            albums.forEach(album => {
                if(!this.genres.includes(album.genre)){
                    this.genres.push(album.genre);
                }
            });
        });
    },
    methods:{
        emitGenre(){
            eventBus.$emit('filters', this.filter);
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/general.scss';
@import '@/style/vars.scss';

label{
    display: inline-block;
    color:$light;
    font-size:.8rem;
    margin-right:20px;
    text-transform: uppercase;
}

select{
    background-color:$primary_dark;
    border:none;
    color:$light;
    padding:5px 25px;
    border-right:25px solid transparent;

    &:focus-visible{
        outline:none;
    }
}

</style>
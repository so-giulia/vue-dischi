<template>
    <div class="col-4 text-align-right">
        <label for="select">Filter by genre</label>
        <select name="genres" id="genres" class="rounded-pill" v-model="filter">
            <option value="all">All</option>
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
    created(){
        eventBus.$on('selectGenre', array =>{
            array.forEach(oggetto => {
                if(!this.genres.includes(oggetto.genre)){
                    this.genres.push(oggetto.genre);
                }
            });
        });
        console.log(this.filters);
        eventBus.$emit('filters', this.filters);
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
<template>
    <div class="col-4 text-align-right">
        <label for="select">Filter by genre</label>
        <select name="genres" id="genres" class="rounded-pill">
            <option></option>
        </select>
    </div>
</template>

<script>
export default {
    name:'Filters'
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
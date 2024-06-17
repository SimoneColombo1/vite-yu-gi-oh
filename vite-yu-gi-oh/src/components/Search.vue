<script>
export default{
    data() {
        return {
            textSearched:"",
        }
    },
}

</script>
<template>
<div class="select">
    <select  @change="$emit('SearchText',textSearched) " v-model="textSearched"   >
       <option value="alien">Alien</option>
       <option value="hero">-Eyes Dragon</option>
       <option value="Noble Knight">Noble Knight</option>

    </select>
</div>
</template>

<style>
.select{
    margin-left: 13.5rem;
    select{
        width: 8rem;
        height: 2rem;
        border: 0;
        margin-top: 1rem;
        border-radius:0.3rem ;
        text-align: center;
    }
}

</style>
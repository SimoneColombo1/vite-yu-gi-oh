<script>
export default{
    data() {
        return {
            
        }

    },
    props:{
    cards:{
        type:Array,
        required:true
    },
    
}
   
}
</script>
<template>
   <section>
<div class="card-container">
     <div class="lenght"> <h3>Found {{ cards.length }} cards</h3> </div>
    <div class="singlecard" v-for="(card, index) in cards" :key="index">
      <span class="card-image"><img :src="card.card_images[0].image_url"></span>
      <span class="card-name"> <h3>{{ card.name }}</h3> </span>
      <span>  {{ card.archetype }}</span>
         </div>
         
    </div>
</section>
</template>
<style>
 section{
    width: 80vw;
  display: flex;
  justify-content: center;
 padding-top: 1rem;
  background-color: white;
  margin-left: 14rem;
  margin-top: 4rem;
 }
.card-container{

width: 90%;
display: flex;
flex-wrap: wrap;
flex-direction: row;
justify-content: center;

.lenght{
    width: 94%;
    background-color:#212529 ;
    color: white;
    font-size: 1rem;
    padding: 1rem;
}

.singlecard{
   margin: 0 1.5rem 4rem 1.5rem;
   background-color: #d48f38;
   display: flex;
   flex-direction: column;
    width:12 rem ;
    height: 20rem;
 
.card-name{
    color: white;
}

   span {
 width: 11rem;
 height: 6rem;
 background-color: #d48f38;
justify-content: center;
 display: flex;
 padding-bottom: 0.5rem;

   }
   
    

.card-image{
    display: flex;
    justify-content: flex-start;
    width: 9rem;
    height: 16rem;
    padding: 0;
}}}
</style>
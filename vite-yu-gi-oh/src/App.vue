<script>
import axios from 'axios';
import cardList from './components/cardList.vue';
import Appheader from './components/AppHeader.vue'
import Search from './components/Search.vue';

export default{
  
  components:{
cardList,
Appheader,
Search
  },
  data() {
    return {
      cards: [],
      cardImage: []
  
      
    }
  },
  methods: {
    getCardList(textSearched){
    
      // Make a request for a user with a given ID
axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=200&offset=0&archetype=' +textSearched )
  .then( (response) => {
    // handle success
    console.log(response.data.data);
    this.cards = response.data.data;
    
  
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .finally(function () {
    // always executed
  });
     
},

SearchText(textSearched){

  this.getCardList(textSearched)
}

},
created() {
    this.getCardList();
    
    
  },
}
</script>


<template>
 <Appheader />
 <main>
 <Search @SearchText="SearchText"/>
  <cardList :cards="cards"/>
</main>
  

</template>

<style scoped lang="scss" >
main{
  background-color: #d48f38;
display: flex;

flex-direction: column;
justify-content: center;
}
</style>


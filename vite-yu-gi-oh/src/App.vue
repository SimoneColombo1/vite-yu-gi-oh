<script>
import axios from 'axios';





export default{
  
  components:{

  },
  data() {
    return {
      cards: [],
      
  
      
    }
  },
  methods: {
    getCardList(){
    
      // Make a request for a user with a given ID
axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
  .then( (response) => {
    // handle success
    console.log(response.data);
    this.cards = response.data;
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .finally(function () {
    // always executed
  });
     
},

},
created() {
    this.getCardList();
    
  },
}
</script>


<template>
  
  
  


</template>

<style scoped>

</style>


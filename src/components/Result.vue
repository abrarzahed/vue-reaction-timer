<template>
  <p>Reaction Time - {{ score }}</p>
  <p class="rank"> {{ rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data (){
       return{
           rank : null
       }
    },
    mounted(){
        if(this.score < 250){
            this.rank = 'Monstar😎'
        }else if(this.score < 400){
            this.rank = 'Rapid Action😲'
        }else{
            this.rank = 'Slow😢'
        }
    }
}
</script>

<style>
.rank{
    font-size: 1.5rem;
    font-weight: bold;
    color: #016d6d;
}

</style>

<template>

<section>

  <h2><span class="bleu">lE COIN CHILL</span> et la buvette </h2>

<!-- <p class="txt">ok</p> -->


<div class="zoneChill">

    <prismic-image  class="zoneChill_image" :field="chillbuvette.data.chill_image" />

        <div class="tkt">

   
    <prismic-rich-text class="zoneChill_texte" :field="chillbuvette.data.chill_texte" />

     <ul class="zoneChill_jeux">
        <li class="zoneChill_jeux_item" v-for="jeu in chillbuvette.data.chill_jeux" :key="jeu.jeux_nom[0].text">
            
          <prismic-image  :field="jeu.jeux_image" />
          <h6>{{ jeu.jeux_nom[0].text }}</h6>
          
        </li>
      </ul>

           </div>

      </div>

<div class="zoneBuvette">

    <prismic-image class="zoneBuvette_image" :field="chillbuvette.data.buvette_image" />

    <prismic-rich-text class="zoneBuvette_texte" :field="chillbuvette.data.buvette_texte" />
</div>

<!-- 
      <li v-for="chill_jeu in chillbuvette.data.chill_jeux">
               

        </li> -->


</section>
</template>


<style  lang="scss">

.zoneChill {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px;
    margin-top: -75px;
    z-index: -1;
    position: relative;

    @include medium {
       flex-direction: row;
       margin-top: 0;
    }
    
    
    &_image {
        width: 100%;
        max-height: 248px;
        object-fit: cover;

        @include medium {
         
        }
         
    }

    &_texte {
        width: 80vw;
        padding: $m-small;
        background-color: $color-gray_darken;

        @include medium {
            width: 41vw;
        }

    }

    &_jeux {
        // display: flex;
        // flex-direction: row;
        // justify-content: center;

    display: flex;
    flex-wrap: wrap;  
    justify-content: space-around;  
    gap: 24px;
      
        &_item {
        margin-top: 15px;
        max-width: 23vw;
        display: flex;
        flex-direction: column;
        align-items: center;
        }
      
    }

}

.zoneBuvette {
    margin-top: 70px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px;

     @include medium {
       flex-direction: row-reverse;
       margin-top: 0;
       justify-content: center;
        margin-top: $m-big;
    }

    &_image {
        width: 100%;
        max-height: 248px;
        object-fit: cover;

        @include medium {
            width: 593px;
            

        }
         
    }

       &_texte {
        width: 80vw;
        padding: $m-small;
        background-color: $color-gray_darken;

        @include medium {
        padding: $m-medium;
        background-color: $color-gray_darken;
        position: relative;
        left: 9vw;   
         width: 41vw;
        }

    }


}


.tkt {
    @include medium {
    //  display: flex;
    }
}



 

</style>


<script setup>
const { client } = usePrismic();



const { data: chillbuvette } = await useAsyncData('chillbuvette', () => client.getSingle('chillbuvette'))

console.log(chillbuvette);

</script>

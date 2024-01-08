<template>
  <i class="icon" :class="className">

    <a :href="url" target="_blank" rel="noopener noreferrer">
    <component :is="getIcon" />
    </a>
  </i>
</template>


<style lang="scss" scoped>
.icon {
  display: inline-flex;
  align-items: center;
  border-radius: 100%;
  height: 42px;
  width: 42px;


   svg {
    scale: 1;
     margin: 8px;
    }

  &.-big {
    height: 85px;
    width: 90px;

    svg {
      scale: 1.5;
    }
  }


//   @include md{

//   }



  &.-blue {
    fill: $color-main;

  }

  &.-white {
    fill: $color-white;
  }

  &.-border {
  border: 2px solid $color-white_darken;


  }


}


 
</style>


<script setup>
import { computed } from 'vue'

import logoFacebook from '../icons/logoFacebook.vue'
import logoInstagram from '../icons/logoInstagram.vue'
import iconLogo from '../icons/iconLogo.vue'
import logoTwitch from '../icons/logoTwitch.vue'
import logoX from '../icons/logoX.vue'


const props = defineProps ({
    name: String,
    size: String,
    color: String,
    border: Boolean,
    url:String,
})


const getIcon = computed(() => {
    switch (props.name) {
        case 'facebook' :
        return logoFacebook
        case 'x' :
        return logoX
        case 'instagram' :
        return logoInstagram
        case 'iconLogo' :
        return iconLogo
        case 'twitch':
        return logoTwitch
         default:
         return logoInstagram
    }
})


const className = computed(() => ({
  '-big': props.size === 'big',
  '-blue': props.color === 'blue',
  '-white': props.color === 'white', 
  '-border': props.border,



}))


</script>
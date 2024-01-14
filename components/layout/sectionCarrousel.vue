<template>
    <section class="my_section section_carrousel">
        <h2 class="bleu section_carrousel-titre">Smash Arena Event</h2>
        
        <swiper-container
            :slides-per-view="1"
            space-between=10
            :centered-slides="true"
            navigation="true" 
            @swiperprogress="onProgress"
            @swiperslidechange="onSlideChange"
            :autoplay="{
                delay: 10000,
                disableOnInteraction: false,
            }"
            >

            <swiper-slide v-for="c in carrousel.data.carrousel_item">
                <PrismicImage class="carrousel_img" :field="c.carrousel_img" />
                <PrismicRichText class="h2 carrousel_titre" :field="c.carrousel_titre" /> 
                <PrismicRichText class="carrousel_texte" :field="c.carrousel_texte" /> 
            </swiper-slide>

        </swiper-container>
    </section>
</template>

<style lang="scss">

.section_carrousel{

    &-titre{
        margin-bottom: 0;
    }

    swiper-container{
        width: 100%;
        max-width: 900px;
        overflow: visible;
        
        swiper-slide{
            position: relative;
    
            .carrousel_titre{
                position: absolute;
                top: 5px;
                left: 50%;
                margin: 0;
                translate: -30% 0;
    
            }
    
            .carrousel_img{
                width: 100;
                aspect-ratio: 16/9;
                object-fit: cover;
                filter: brightness(90%);
            }
            
            .carrousel_texte{
                width: 90%;
                margin: auto;
    
                padding: $m-small $m-litle;
                background: $color-gray_darken;

                strong {
                    font-weight: $font_weight-bold;
                    color: $color-main;
                }

                ul{
                    padding-left: $m-small;
                    list-style: inside;
                }
            }
        }
    }

    @include medium{
        swiper-container{
            aspect-ratio: 16/9.5;
            
            swiper-slide{
                position: relative;
        
                .carrousel_titre{
                    position: absolute;
                    top: $m-small;
                    left: 40%;
        
                }
        
                .carrousel_img{
                    aspect-ratio: 16/9;
                }
                
                .carrousel_texte{
                    position: absolute;
                    top: auto;
                    bottom: 0%;
                    right: 5%;
                    width: 60%;
                }
            }
        }
    }
}

</style>

<script>
// import function to register Swiper custom elements
import { register } from 'swiper/element/bundle';

// register Swiper custom elements
register();

export default {
    setup(){
        const onProgress = (e) => {
            const [swiper, progress] = e.detail;
            // console.log(progress)
        };

        const onSlideChange = (e) => {
            // console.log('slide changed')
        }

        return {
            onProgress,
            onSlideChange,
        };
    }
}

</script>

<script setup>
// import de Prismic
const { client } = usePrismic();

// import du document Règles
const { data: carrousel, error: carrousel_error } = await useAsyncData("carrousel", () =>
    client.getSingle("carrousel")
)

if (!carrousel.value || carrousel_error.value){
    throw createError({statusCode: 404, statusMessage: "Prismic n'a pas trouvé la section carrousel"})
}
</script>

<template>
    <section class="section_sponsors">
        <h2><span class="bleu">Nos</span> Sponsors</h2>

        <div class="section_sponsors-div">
            <ul class="section_sponsors-div-liste">
                <li v-for="sponsor in sponsors.data.sponsor" class="section_sponsors-div-liste-item">
                    <PrismicImage class="section_sponsors-div-liste-item_image" :field="sponsor.sponsor_image"/>
                </li>
            </ul>
        </div>
    </section>
</template>

<style lang="scss">
.section_sponsors{

    &-div{
        &::before,
        &::after{
            content: "";
            display: block;
            width: 100%;
            height: 2px;
            background: $color-main;
            margin: $m-small 0;
        }

        &-liste{
            background: white;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-evenly;
            align-items: center;
            gap: 5px;
            padding: $m-small;
    
            &-item{
                
                &_image{
                    width: 150px;
                    aspect-ratio: 2/1;
                    object-fit: contain;
                }
            }
    
            @include medium{
                padding: $m-medium;
                
                &-item{
                    &_image{
                        width: 200px;
                    }
                }
            }
        }
    }
    
}
</style>

<script setup>
const { client } = usePrismic();
const { data: sponsors, error: sponsor_error } = await useAsyncData('sponsors', () => client.getSingle('sponsors'))

if (!sponsors.value || sponsor_error.value){
  throw createError({statusCode: 404, statusMessage: "Prismic n'a pas trouvé la section Sponsors"})
}
</script>
<template>

<div v-for="element in elements">
<PrismicRichText :field="element.groupe_texte"/>


</div>

</template>


<style lang="scss">
 </style>


<script setup>
const { client } = usePrismic();
const { data: accueil } = await useAsyncData('accueil', () => client.getSingle('accueil'))

const props =defineProps ({
    elements: Array

})


</script>
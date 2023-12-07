<template>
<h1>hello</h1>
<!-- <h2 class="test">test</h2> -->



 <LayoutMyHero :elements="accueil.data.groupe"/>


 

</template>

<style lang="scss" scoped>

.test {
    text-align: center;
  color: $color-main;
}

</style>

<script setup>

const { client } = usePrismic();
const { data: accueil } = await useAsyncData('accueil', () => client.getSingle('accueil'))

// console.log(accueil.data.texte)


// const { data: home, error } = await useAsyncData("home", () =>
//   client.getSingle("accueil")
// );

// if (!home.value || error.value) {
//   throw createError({
//     statusCode: 404,
//     statusMessage: "la page d\accueil est introuvable",
//   });
// }

</script>
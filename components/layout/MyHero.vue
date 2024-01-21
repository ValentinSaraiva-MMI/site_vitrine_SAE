<template>
  <div class="hero">
    <div class="hero_left" v-for="element in elements">
      <PrismicImage
        :field="element.hero_background_mobile"
        class="hero_backgroundmobile"
      />
      <!-- <PrismicRichText :field="element.hero_background_pc"/> -->
      <PrismicRichText :field="element.hero_title" class="hero_title" />
      <PrismicRichText :field="element.hero_texte" class="hero_texte" />
      <myButton
        class="hero_btn"
        lien="https://tournois.smash-arena-event.fr"
        size="big"
        color="blue"
        >Je m’inscris</myButton
      >
    </div>

    <p class="hero_backgrounddesktop">
      À VOS <br />
      MANETTES
    </p>

    <div>
      <img class="hero_img" :src="imgHeroAffiche" alt="" />
    </div>
  </div>
</template>

<style lang="scss">
.hero {
  @include medium {
    display: flex;
  }

  &_left {
    @include medium {
      width: 50vw;
      margin-left: 9.385vw;
    }
  }

  &_backgroundmobile {
    position: absolute;
    z-index: 0;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -100%);

    @include medium {
      display: none;
    }
  }

  &_backgrounddesktop {
    display: none;

    @include medium {
      z-index: -1;
      display: block;
      position: absolute;
      top: 190px;
      font-size: 10.75em;
      font-family: $font-title;
      color: rgba(148, 148, 148, 0.05);
    }

    @include large {
      font-size: 11.75em;
    }
  }

  &_title {
    z-index: 1;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    text-align: center;
    justify-content: center;
    padding: 20% 0px 0px;

    strong {
      color: $color-main;
    }

    @include large {
      text-align: left;
    }
  }

  &_texte {
    position: relative;
    z-index: 1;
    width: 19em;
    left: 50%;
    transform: translateX(-50%);
    text-align: center;

    strong {
      font-weight: 800;
    }

    @include large {
      display: flex;
      text-align: left;
      width: 560px;
      transform: translateX(0%);
      left: 0%;
    }
  }

  &_btn {
    display: flex;
    justify-content: center;
    margin: $m-litle 0px 5px;

    @include large {
      justify-content: left;
      margin: $m-medium 0px 5px;
    }
  }

  &_img {
    width: 90%;

    @include medium {
      width: 100%;
    }
  }
}
</style>

<script setup>
const { client } = usePrismic();
const { data: accueil } = await useAsyncData("accueil", () =>
  client.getSingle("accueil")
);

// console.log(accueil)

const props = defineProps({
  elements: Array,
});

// variable qui contient le lien de l'image aléatoire
const imgHeroAffiche = ref("");

// tableau de toutes les images possibles
const imgHero = [
  "/imgHero/cloud.png",
  "/imgHero/duo.png",
  "/imgHero/falco.png",
  "/imgHero/pikachu.png",
  "/imgHero/felinferno.png",
  "/imgHero/ike.png",
  "/imgHero/kirby.png",
  "/imgHero/kong.png",
  "/imgHero/link.png",
  "/imgHero/lucas.png",
  "/imgHero/marie.png",
  "/imgHero/mewtwo.png",
  "/imgHero/peach.png",
  "/imgHero/pit.png",
  "/imgHero/pyra.png",
  "/imgHero/ridley.png",
  "/imgHero/rob.png",
  "/imgHero/wario.png",
  "/imgHero/zelda.png",
];

// fonction qui attribue un lien aléatoirement à la constante "imgHeroAffiche"
const HeroImgAleatoire = () => {
  let randomNum = Math.floor(Math.random() * imgHero.length);
  imgHeroAffiche.value = imgHero[randomNum];
};

onMounted(() => {
  // Site Vitrine
  HeroImgAleatoire();

  //   CompteARebours();

  //   // appelle la fonction CompteARebours toutes les secondes
  //   const CompteAReboursInterval = setInterval(CompteARebours, 1000);

  //   onBeforeUnmount(() => {
  //     clearInterval(CompteAReboursInterval);
  //   });
});
</script>

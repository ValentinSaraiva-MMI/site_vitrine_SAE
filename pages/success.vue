<template>
  <div class="succes">
    <div class="succes_div1">
      <h1 class="succes_title"><span class="bleu">M</span>essage Envoyé</h1>
      <p class="succes_description">
        Votre mail a bien été transmis. Nous vous répondrons dans les prochains
        jours.
      </p>

      <myButton url="/" size="big" color="blue" class="button1"
        >Retourner à l'accueil</myButton
      >
    </div>

    <div class="succes_div2">
      <img
        class="succes_div2_image"
        src="/img/letter.webp"
        alt="image representant une lettre avec le logo de super smash bros"
      />
    </div>

    <myButton url="/" size="big" color="blue" class="button2"
      >Retourner à l'accueil</myButton
    >
  </div>
</template>

<style lang="scss">
.succes {
  @include medium {
    display: flex;
  }

  &_title {
    text-align: center;
  }

  &_description {
    text-align: center;
    padding: 0 $m-litle;
  }

  &_div1 {
    @include medium {
      width: 45%;
      display: flex;
      flex-direction: column;
      gap: 20px;
    }
  }

  &_div2 {
    @include medium {
      margin: auto;
    }

    &_image {
      margin: 50px 0;

      @include medium {
        width: 43vw;
      }
    }
  }
}

.button1 {
  display: none;

  @include medium {
    display: flex;
    justify-content: center;
    margin-top: 30px;
  }
}

.button2 {
  @include medium {
    display: none;
  }

  display: flex;
  justify-content: center;
  margin-top: 30px;
}
</style>

<script></script>

<template>
  <section class="my_section section_inscription">
    <h2><span class="bleu">Tu veux participer ?</span> Inscris-toi !</h2>

    <div class="section_inscription-image">
      <div class="section_inscription-image_joueur">
        <h3 class="bleu">Comme Joueur</h3>
        <p>et participe au tournois.</p>
        <myButton
          class="section_inscription-bouton"
          lien="https://tournois.smash-arena-event.fr"
          size="big"
          >Je m'inscris</myButton
        >
        <img
          src="/img/persos.png"
          alt="image de fond des personnage de Smash Bros Ultimate"
        />
      </div>

      <div class="section_inscription-image_benevole">
        <h3 class="bleu">Comme Bénévole</h3>
        <p>et viens nous aider à géré l'évènement.</p>
        <myButton
          class="section_inscription-bouton"
          lien="https://form.jotform.com/240052447803046"
          >Je m'inscris</myButton
        >
        <img src="/img/benevole.jpg" alt="image de fond de bénévoles" />
      </div>
    </div>
  </section>
</template>

<style lang="scss">
.section_inscription {
  overflow: hidden;

  padding-left: 0;
  padding-right: 0;

  &-image {
    width: 100%;
    height: 70vh;
    display: flex;
    flex-direction: column;

    > * {
      position: relative;
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 5px;
      padding: 0 $m-medium;
      transition: all 0.2s ease-in-out;

      h3,
      p,
      img {
        transition: all 0.2s ease-in-out;
      }

      img {
        position: absolute;
        top: 0;
        left: 0;
        z-index: -1;
        opacity: 0.2;
        width: 100%;
        height: 100%;
        object-fit: cover;
      }

      &:hover {
        h3 {
          @include h2;
        }

        p {
          font-size: $mobile-font_semibig;
        }

        img {
          opacity: 0.3;
        }
      }
    }

    &_joueur {
      align-items: flex-start;
      flex: 1 1 60%;

      .section_inscription-bouton {
        margin-top: 30px;
      }
    }

    &_benevole {
      align-items: flex-end;
      flex: 1 1 40%;
      background: rgba($color-main, 20%);

      h3,
      p {
        text-align: right;
      }

      .section_inscription-bouton {
        margin-top: 20px;
      }
    }

    @include large {
      flex-direction: row;

      > * {
        gap: $m-small;
        padding: $m-medium;

        h3 {
          @include h2;
        }

        &:hover {
          padding: $m-big;

          h3 {
            @include h1;
          }

          p {
            font-size: $pc-font_semibig;
          }
        }
      }

      &_joueur {
        justify-content: start;
        align-items: flex-start;
      }

      &_benevole {
        justify-content: flex-end;
        align-items: flex-end;

        &:hover {
          flex: 1 1 66%;
        }
      }
    }
  }
}
</style>

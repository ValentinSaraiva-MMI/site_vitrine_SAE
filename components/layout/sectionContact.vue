<template>
  <section id="section-contact" class="my_section">
    <h2><span class="bleu">nous</span> contacter</h2>

    <form
      class="formulaire"
      action="https://api.web3forms.com/submit"
      method="POST"
    >
      <input
        type="hidden"
        name="access_key"
        value="2e16caef-865b-4105-80bf-cafccea701be"
      />

      <div class="formulaire_section1">
        <div class="formulaire_section1_div1">
          <input
            type="text"
            placeholder="Nom "
            class="input1"
            name="nom"
            required
          />
        </div>

        <div class="formulaire_section1_div2">
          <input
            type="email"
            class="input2"
            placeholder="Email "
            name="email"
            required
          />
        </div>
      </div>

      <div class="formulaire_section2">
        <textarea
          placeholder="Message"
          rows="8"
          class="formulaire_section2_textarea"
          name="message"
          required
        ></textarea>
      </div>

      <div class="formulaire_boutons">
        <button
          name="redirect"
          value="https://edition2024.smash-arena-event.fr/success"
          type="submit"
          class="banger"
        >
          <h6 class="banger-text">Envoyer</h6>
        </button>

        <myButton class="hero_btn" url="/" size="big">F.A.Q </myButton>
      </div>
    </form>
  </section>
</template>

<style lang="scss">
.banger {
  padding: $m-litle $m-small + 15;
  min-width: 150px;
  margin-top: 15px;
  flex: none;
  display: inline-flex;

  height: fit-content;
  transform: skewX(-25deg);
  text-align: center;
  background: $color-main;
  color: $color_white;
  transition: all 0.1s linear;
  cursor: pointer;

  &-text {
    width: 100%;
    transform: skewX(25deg);
  }

  &:hover {
    background: $color-white_darken;
  }

  @include medium {
    margin-top: 35px;
    padding: $m-small $m-small + 10;

    &.-big {
      padding: $m-litle $m-litle + 15;
    }
  }
}

.formulaire {
  width: 83vw;
  margin: auto;

  &_section1 {
    display: flex;
    flex-wrap: wrap;

    @include medium {
      flex-wrap: nowrap;
      gap: 50px;
    }

    &_div1 {
      width: 100vw;
      margin-bottom: 35px;
      // padding: 0 15px;
      @include medium {
        width: 50%;
      }
    }

    &_div2 {
      width: 100vw;
      margin-bottom: 35px;

      @include medium {
        width: 50%;
      }
    }
  }

  &_section2 {
    display: flex;
    flex-wrap: wrap;

    &_textarea {
      width: 100%;
      display: block;
      margin-top: 15px;
      margin-bottom: 20px;
      padding: 10px 15px;
      background: none;
      border: none;
      border-bottom: 2px solid #fff;
      color: #fff;

      @include medium {
        border-left: 2px solid #fff;
      }
    }
  }

  &_boutons {
    display: flex;
    gap: 20px;
    align-items: center;
  }

  .input2,
  .input1 {
    width: 100%;
    display: block;
    margin-top: 15px;
    margin-bottom: 20px;
    padding: 10px 15px;
    background: none;
    border: none;
    border-bottom: 2px solid #fff;
    color: #fff;
  }
}
</style>

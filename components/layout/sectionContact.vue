<template>
  <section class="my_section">
    <h2><span class="bleu">nous</span> contacter</h2>

    <form class="formulaire" method="POST">
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
        <myButton class="hero_btn bouton" url="/" size="big" color="blue"
          >Envoyer</myButton
        >
        <myButton class="hero_btn" url="/" size="big">F.A.Q</myButton>
      </div>
    </form>
  </section>
</template>

<style lang="scss">
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
      border-left: 2px solid #fff;
    }
  }

  &_boutons {
    display: flex;
    gap: 20px;
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

<script setup></script>

<template>
  <div class="wrapper">
    <div id="javascriptComponents">
      <div class="md-layout">
        <div class="md-layout-item md-size-66 mx-auto md-small-size-100">
          <md-card>
            <carousel
              :per-page="1"
              loop
              :speed="700"
              autoplay
              :autoplay-timeout="5000"
              :mouse-drag="false"
            >
              <slide>
                <div class="carousel-caption">
                  <h4>
                    "L'amour pour toute les créatures vivantes est le plus noble des attributs de l'Homme"
                    <br/>
                    <md-icon>eco</md-icon>
                    <br/>
                    -Charles Darwin-
                  </h4>
                </div>
                <img :src="carousel1" alt="carousel1" />
              </slide>
              <slide>
                <div class="carousel-caption">
                  <h4>
                    "Le but de la vie est le développement personnel. Parvenir à une parfaite réalisation de sa nature, c'est pour cela que nous sommes tous ici."
                    <br/>
                    <md-icon>shop</md-icon>
                    <br/>-Oscar Wilde-
                  </h4>
                </div>
                <img :src="carousel2" alt="carousel2" />
              </slide>
              <slide>
                <div class="carousel-caption">
                  <h4>
                    Rien n'est solitaire, tout est solidaire. L'homme est solidaire avec la planète, la planète est solidaire avec le soleil, le soleil est solidaire avec l'étoile, 
                    l'étoile est solidaire avec la nébuleuse, la nébuleuse, groupe stellaire, est solidaire avec l'infini.
                    <br/>
                    <md-icon>groups</md-icon>
                    <br/>-Victor Hugo-
                  </h4>
                </div>
                <img :src="carousel3" alt="carousel3" />
              </slide>
            </carousel>
          </md-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {
  },
  data() {
    return {
      classicModal: false,
      selectedDate: new Date("2018/03/26"),
      carousel1: require("@/assets/img/nature-2.jpg"),
      carousel2: require("@/assets/img/nature.jpg"),
      carousel3: require("@/assets/img/nature-3.jpg")
    };
  },
};
</script>

<template>
  <div class="wrapper">
    <parallax class="page-header header-filter" :style="headerStyle">
      <div class="md-layout">
        <div class="md-layout-item">
          <div class="image-wrapper">
            <img :src="leaf4" alt="leaf4" class="leaf4" v-show="leafShow" />
            <img :src="leaf3" alt="leaf3" class="leaf3" v-show="leafShow" />
            <img :src="leaf2" alt="leaf2" class="leaf2" v-show="leafShow" />
            <img :src="leaf1" alt="leaf1" class="leaf1" v-show="leafShow" />
            <div class="brand">
              <h1>GREEN TECH</h1>
              <h3>Création de site internet sur mesure</h3>
            </div>
          </div>
        </div>
      </div>
    </parallax>
    <div class="main main-raised">
      
      <div class="section">
        <div class="md-layout">
            <div
              class="md-layout-item md-size-66 md-xsmall-size-100 mx-auto text-center"
            >
              <h2 class="title text-center">Qui sommes nous ?</h2>
              
              <h5 class="description">
                Fondé en 2012 par Olivier Legirond et sa femme Nessa, Green Tech et une agence digitale aux valeurs écologiques fortes. Nous 
                soutenons en priorités les sart-ups, entreprises ou associations ayant au centre de leur activité la volonté d'agir en faveur de l'environement 
                et pour une économie inclusive. Basé au coeur du perche, Green Tech s'est donné pour mission la création de site internet qui participeront 
                aux changements de demain.
              </h5> 
            </div>
          </div>
      </div>

      <div class="section section-javascript">
        <div class="container">
          <javascript-components></javascript-components>
        </div>
      </div>
      
      <div class="section section-signup page-header" :style="signupImage">
        <div class="container">
          <div class="md-layout">
            <div rgdffer
              class="md-layout-item md-size-33 md-medium-size-40 md-small-size-50 md-xsmall-size-70 mx-auto text-center"
            >
            </div>
          </div>
        </div>
      </div>
      
      
    </div>
  </div>
</template>

<script>
import JavascriptComponents from "./components/JavascriptComponentsSection";
export default {
  components: {
    JavascriptComponents,
  },
  name: "index",
  bodyClass: "index-page",
  props: {
    image: {
      type: String,
      default: require("@/assets/img/vue-mk-header.jpg")
    },
    leaf4: {
      type: String,
      default: require("@/assets/img/leaf4.png")
    },
    leaf3: {
      type: String,
      default: require("@/assets/img/leaf3.png")
    },
    leaf2: {
      type: String,
      default: require("@/assets/img/leaf2.png")
    },
    leaf1: {
      type: String,
      default: require("@/assets/img/leaf1.png")
    },
    signup: {
      type: String,
      default: require("@/assets/img/city.jpg")
    },
    landing: {
      type: String,
      default: require("@/assets/img/landing.jpg")
    },
    profile: {
      type: String,
      default: require("@/assets/img/profile.jpg")
    }
  },
  data() {
    return {
      firstname: null,
      email: null,
      password: null,
      leafShow: false
    };
  },
  methods: {
    leafActive() {
      if (window.innerWidth < 768) {
        this.leafShow = false;
      } else {
        this.leafShow = true;
      }
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.image})`
      };
    },
    signupImage() {
      return {
        backgroundImage: `url(${this.signup})`
      };
    }
  },
  mounted() {
    this.leafActive();
    window.addEventListener("resize", this.leafActive);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.leafActive);
  }
};
</script>
<style lang="scss">
.section-download {
  .md-button + .md-button {
    margin-left: 5px;
  }
}
.section-signup {
  border-bottom-right-radius: 6px;
  border-bottom-left-radius: 6px;
}

@media all and (min-width: 991px) {
  .btn-container {
    display: flex;
  }
}
.section-javascript {
  margin-bottom: -15%;
}
</style>

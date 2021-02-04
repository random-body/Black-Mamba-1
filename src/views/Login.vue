<template>
  <div class="wrapper">
    <div class="section page-header header-filter" :style="headerStyle">
      <div class="container">
        <div class="md-layout">
          <div
            class="md-layout-item md-size-33 md-small-size-66 md-xsmall-size-100 md-medium-size-40 mx-auto"
          >
            

        <div class="container-contact2">
          <h3>Be wild</h3>
        
          <div class="wrap-contact2">
            <form class="contact2-form validate-form contact-form" @submit.prevent="sendEmail">
            <span class="contact2-form-title">Contactez nous</span>
            <div class="wrap-input2 validate-input" data-validate="Nom requis">
              <md-icon class="md1">face</md-icon>
              <input placeholder="Nom ou entreprise..." class="input2" type="text" name="user_name" required>
              
            </div>
            <div class="wrap-input2 validate-input" data-validate="Email valide requis">
              <md-icon class="md1">email</md-icon>
              <input placeholder="Email..." type="text" name="user_email" class="input2" required>
              
            </div>
            <div class="wrap-input2 validate-input" data-validate="Message requis">
              <md-icon class="md">chat</md-icon>
              <textarea required placeholder="Message..." name="message" id="" cols="30" rows="10"></textarea>
              
            </div>
            <div class="container-contact2-form-btn">
              <div class="wrap-contact2-form-btn">
                <div class="contact2-form-bgbtn">
                </div>
                <input class="button" type="submit" value="ENVOYER">
              </div>
            </div>
            </form>
          </div>

    </div>



  <transition name="modal" class="modal">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <div class="modal-container" v-click-outside="closeModal">
          <div class="modal-header">
            <slot name="header"></slot>
          </div>

          <div class="modal-body text-center">
            <slot name="body">Message envoyé avec succé!</slot>
          </div>

          <div class="modal-footer" onClick="window.location.reload();">
            <slot name="footer">Fermer</slot>
          </div>
        </div>
      </div>
    </div>
  </transition>



          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import emailjs from 'emailjs-com';

export default {
  components: {
  },
  methods: {
    sendEmail: (e) => {
      emailjs.sendForm('service_7478cc7', 'template_citvyyk', e.target, 'user_95rIKetMNewyJMN5Q18WC')
        .then((result) => {
            console.log('SUCCESS!', result.status, result.text);
            window.location.reload();
        }, (error) => {
            console.log('FAILED...', error);
        });
    },
    closeModal: function() {
      this.$emit("close");
    }
  },
  bodyClass: "login-page",
  data() {
    return {
      firstname: null,
      email: null,
      password: null
    };
  },
  props: {
    header: {
      type: String,
      default: require("@/assets/img/profile_city.jpg")
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.header})`
      };
    }
  }
};
</script>

<style lang="css">
.container-contact2 {
  background-color: white;
  padding: 40px;
  text-align: center;
  border-radius: 7px;
}
.container-contact2 h3 {
  color: rgba(0, 0, 0, 0.575);
  font-size: 17px;
}
input {
  width: 100%;
  padding: 15px;
  border-top: white;
  border-left: white;
  border-right: white;
  border-bottom: solid rgba(0, 0, 0, 0.479) 1px;
  color: black;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 14px;
}
textarea {
  width: 100%;
  padding: 15px;
  border-top: white;
  border-left: white;
  border-right: white;
  border-bottom: solid rgba(0, 0, 0, 0.438) 1px;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 14px;
}
.wrap-input2 {
  margin-top: 10px;
  margin-bottom: 10px;
  display: flex;
  font-size: 14px;
}
.md {
  margin-top: 12px!important;
  color: black!important;
}
.md1 {
  margin-top: 12px!important;
  color: black!important;
}
.button {
  color: #4caf50!important;
  border: none;
  background-color: white;
  font-family: Arial, Helvetica, sans-serif;
  padding: 17px;
  cursor: pointer;
}
.modal-body {
  color: black;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 15px;
}
.modal-footer {
  color: red;
  cursor: pointer;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 15px;
}
.modal-enter {
  opacity: 0;
}
.modal-leave-active {
  opacity: 0;
}
.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
.modal-wrapper {
  display: none!important;
}
.modal-mask {
  display: none!important;
}
</style>

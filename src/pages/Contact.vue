<template>
  <div class="container">
    <div class="row">
      <div class="col-7">
        <form class="vue-form" @submit.prevent="submit">
          <div class="error-message">
            <p v-show="!email.valid">Por favor, insira um email válido.</p>
          </div>
          <fieldset>
            <legend>Entre em contato conosco agora!</legend>
            <div>
              <label class="label" for="name">Nome</label>
              <input type="text" name="name" id="name" required="" v-model="name">
            </div>
            <div>
              <label class="label" for="email">Email</label>
              <input type="email" name="email" id="email" required=""
                :class="{ email , error: !email.valid }"
                v-model="email.value">
            </div>
            <div>
              <label class="label" for="subject">Assunto</label>
              <input type="text" name="subject" id="subject" required="" v-model="subject">
            </div>
            <div>
              <label class="label" for="textarea">Escreva a sua mensagem</label>
              <textarea class="message" name="textarea" id="textarea" required="" 
                v-model="message.text" 
                :maxlength="message.maxlength"></textarea>
              <span class="counter">{{ message.text.length }} / {{ message.maxlength }}</span>
            </div>
            <div>
              <input type="submit" value="Enviar">
            </div>
          </fieldset>
        </form>
        <!-- <div class="debug">
          <pre><code>{{ $data }}</code></pre>
        </div> -->
      </div>
      <div class="col-5">
        <div class="social-media">
          <fieldset>
            <legend>Visite nossas redes sociais!</legend>
            <ul class="media-list">
              <li class="facebook"><i class="fab fa-facebook-square"></i> Facebook</li>
              <li class="instagram"><a href="https://www.instagram.com/flyagenciadigital/"><i class="fab fa-instagram"></i> Instagram</a></li>
              <li class="twitter"><i class="fab fa-twitter"></i> Twitter</li>
              <li class="whatsapp"><a href="https://api.whatsapp.com/send?phone=5567992328774"><i class="fab fa-whatsapp"></i> WhatsApp</a></li>
            </ul>  
          </fieldset>
        </div>
      </div>
    </div>
    </div>
</template>

<script>
var emailRegExp = /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/;
export default {
  name: 'Contact',
  data: function() {
    return {
      name: "",
      email: {
        value: "",
        valid: true
      },
      subject: "",
      message: {
        text: "",
        maxlength: 500
      },
      submitted: false
    };
  },
  methods: {
    // submit form handler
    submit: function() {
      this.submitted = true;
    },
    // validate by type and value
    validate: function(type, value) {
      if (type === "email") {
        this.email.valid = this.isEmail(value) ? true : false;
      }
    },
    // check for valid email adress
    isEmail: function(value) {
      return emailRegExp.test(value);
    }
  },
  watch: {
    // watching nested property
    "email.value": function(value) {
      this.validate("email", value);
    }
  }
}

</script>

<style scoped>
  @import url("https://fonts.googleapis.com/css?family=Source+Code+Pro:300,400");

  *,
  *::after,
  *::before {
  box-sizing: border-box;
  }
  
html,
.container {
  min-height: 100vh;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
  Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", Helvetica, Arial,
  sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.center {
  display: flex;
  justify-content: center;
  align-items: center;
}

a {
  color: #2c3e50;
  text-decoration: none;
}
ul {
  align-content: center;
}
li {
  display: block;
  margin: 30px auto;
  padding-left: 40%;
  text-align: justify;
  font-size: 20px;
  
}

vue-form, 
social-media {
  font-size: 16px;
  width: 500px;
  padding: 15px 30px;
  border-radius: 4px;
  margin: 50px auto;
  width: 500px;
  background-color: #fff;
  box-shadow: 0 4px 6px 0 rgba(0, 0, 0, 0.3);
}

.social-media {
  padding-top: 35px;
}
.fab {
  font-size: 25px; 
}

.fa-whatsapp {
  color: #25D366;
}
.fa-instagram {
  color: #dc2743;
}
.fa-facebook-square {
  color: #3b5998	;
}
.fa-twitter {
  color: #1DA1F2;
}

.vue-form fieldset,
.social-media fieldset {
  margin: 24px 0 0 0;
}
.vue-form legend,
.social-media legend {
  padding-bottom: 10px;
  border-bottom: 1px solid #ecf0f1;
}

.vue-form div,
.social-media div {
  position: relative;
  margin: 20px 0;
}
.vue-form .label {
  display: block;
  text-align: left;
    color: #94aab0;
  margin-bottom: 10px;
}
.vue-form input,
.vue-form textarea,
.vue-form label {
  color: #2b3e51;
}
.vue-form input[type="text"],
.vue-form input[type="email"],
.vue-form textarea,
.vue-form legend {
  display: block;
  width: 100%;
  appearance: none;
}
.vue-form input[type="text"],
.vue-form input[type="email"],
.vue-form textarea {
  padding: 12px;
  border: 1px solid #cfd9db;
  background-color: #ffffff;
  border-radius: 0.25em;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.08);
}
.vue-form input[type="text"]:focus,
.vue-form input[type="email"]:focus,
.vue-form textarea:focus {
  outline: none;
  border-color: #2c3e50;
  box-shadow: 0 0 5px rgba(44, 151, 222, 0.2);
}
.vue-form .vue-form-list {
  margin-top: 16px;
}
.vue-form .vue-form-list::after {
  clear: both;
  content: "";
  display: table;
}
.vue-form .vue-form-list li {
  display: inline-block;
  position: relative;
  user-select: none;
  margin: 0 26px 16px 0;
}

.vue-form textarea {
  min-height: 120px;
  resize: vertical;
  overflow: auto;
}
.vue-form input[type="submit"] {
  border: none;
  background: #2c3e50;
  border-radius: 0.25em;
  padding: 12px 20px;
  color: #ffffff;
  font-weight: bold;
  float: right;
  cursor: pointer;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  appearance: none;
}
.no-touch .vue-form input[type="submit"]:hover {
  background: #42a2e1;
}
.vue-form input[type="submit"]:focus {
  outline: none;
  background: #2b3e51;
}
.vue-form input[type="submit"]:active {
  transform: scale(0.9);
}
.vue-form .error-message {
  height: 35px;
  margin: 0px;
}
.vue-form .error-message p {
  background: #e94b35;
  color: #ffffff;
  font-size: 1.4rem;
  text-align: center;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  border-radius: 0.25em;
  padding: 16px;
}
.vue-form .error {
  border-color: #e94b35 !important;
}
.vue-form .counter {
  background-color: #ecf0f1;
  position: absolute;
  right: 0px;
  top: 0px;
  font-size: 10px;
  padding: 4px;
}

.debug {
  border-radius: 4px;
  margin: 50px auto;
  width: 500px;
  background-color: #000;
  padding: 50px;
  background: rgba(0, 0, 0, 0.8);
  box-shadow: 0 4px 6px 0 rgba(0, 0, 0, 0.3);
}

.debug pre {
  color: #ffffff;
  font-size: 18px;
  line-height: 30px;
  font-family: "Source Code Pro", monospace;
  font-weight: 300;
  white-space: pre-wrap;
}

@-webkit-keyframes cd-bounce {
  0%,
  100% {
    -webkit-transform: scale(1);
  }
  50% {
    -webkit-transform: scale(0.8);
  }
}
@-moz-keyframes cd-bounce {
  0%,
  100% {
    -moz-transform: scale(1);
  }
  50% {
    -moz-transform: scale(0.8);
  }
}
@keyframes cd-bounce {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(0.8);
  }
}

</style>

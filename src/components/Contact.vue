<script>
import VueRecaptcha from 'vue-recaptcha';

export default {
    name: 'Contact',
    components: {
      VueRecaptcha
    },
    data() {
      return {
        name: '',
        nameRules: [
          v => !!v || 'Name is required',
          v => (v && v.length <= 35) || 'Name must be less than 35 characters'
        ],
        email: '',
        emailRules: [
          v => !!v || 'E-mail is required',
          v => /.+@.+/.test(v) || 'E-mail must be valid'
        ],
        message: '',
        messageRules: [
          v => !!v || 'Message is required'
        ],
        form: false,
        isLoading: false,
        emailSuccess: false,
        emailFailure: false,
        siteKey: process.env.VUE_APP_SITE
      }
    },
    methods: {
      submit () {
        this.$refs.recaptcha.execute();
      },
      onCaptchaVerified(recaptchaToken) {
        this.$refs.recaptcha.reset();
        this.sendEmail(this.name, this.email, this.message, recaptchaToken);
      },
      onCaptchaExpired() {
        this.$refs.recaptcha.reset();
      },
      sendEmail(name, fromEmail, message, token) {
        this.isLoading = true;
        var requestData = {
          'from_email': fromEmail,
          'from_name': name,
          'message_html': message,
          'g-recaptcha-response': token
        };

        window.emailjs.send('gmail', 'template_sLOUmlXD', requestData)
        .then(response => {
          if(response.status === 200) {
            this.emailSuccess = true;
            this.reset();
          } else {
            this.emailFailure = true;
          }
        }).catch(error => {
          console.log(error);
        }).then(() => {
          this.isLoading = false;
        });
      },
      reset() {
        this.$refs.contactForm.reset()
      },
      resetValidation () {
        this.$refs.contactForm.resetValidation()
      }
    }
}
</script>

<template>
    <v-container grid-list-lg id="ContactForm">
        <v-layout row>
            <v-flex class="display-2 text-xs-center my-5 grey--text text--darken-3">Contact Us</v-flex>
        </v-layout>
        <v-layout row>
            <v-flex xs12 sm12 md12>
                <p class="grey--text text--darken-3 subheading mt-3">
                Interested in any of the services available or would like to know more? Get in touch below!</p>
                <p class="grey--text text--darken-3 subheading mt-3">
                Give us a call at 720-336-8806 or submit an inquiry below!</p>

                <v-form ref="contactForm" v-model="form">
                    <v-text-field v-model="name" :rules="nameRules" :counter="35" label="Name" required></v-text-field>
                    <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>
                    <v-textarea v-model="message" :rules="messageRules" auto-grow box class="form-message" label="Message" rows="4" required></v-textarea>
                    <vue-recaptcha class="captcha-badge" ref="recaptcha" @verify="onCaptchaVerified" @expired="onCaptchaExpired" size="invisible" :sitekey="siteKey" badge="inline">
                    </vue-recaptcha>
                    <v-btn class="grey--text text--darken-3" @click="reset" :disabled="isLoading">Clear</v-btn>
                    <v-btn :disabled="!form" :loading="isLoading" class="white--text" color="deep-purple darken-1" depressed @click="submit">Submit</v-btn>
                </v-form>
                <v-alert v-model="emailSuccess" dismissible type="success">
                  Your inquiry has been sent! We'll get back to you shortly.
                </v-alert>
                <v-alert v-model="emailFailure" dismissible type="error">
                  Oops, something went wrong. Please submit your request again or try again later.
                </v-alert>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<style scoped>
    .form-message {
        margin-top: 5px;
    }

    .captcha-badge {
      display: none;
    }
</style>
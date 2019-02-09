<script>
export default {
    name: 'Contact',
    $_veeValidate: {
      validator: 'new'
    },

    data: () => ({
      name: '',
      email: '',
      message: '',
      dictionary: {
        attributes: {
          email: 'E-mail Address'
          // custom attributes
        },
        custom: {
          name: {
            required: () => 'Name can not be empty',
            max: 'The name field may not be greater than 35 characters'
            // custom messages
          },
          message: {
              required: () => 'Message can not be empty'
          }
        }
      },
      rules: {
        email: v => (v || '').match(/@/) || 'Please enter a valid email'
      },
      form: false,
      isLoading: false,

    }),
    mounted () {
      this.$validator.localize('en', this.dictionary)
    },
    methods: {
      submit () {
        this.$validator.validateAll();
        //if valid form then send email to send grid service
      },
      clear () {
        this.name = ''
        this.email = ''
        this.message = ''
        this.$validator.reset()
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

                <v-form v-model="form">
                    <v-text-field
                        v-model="name"
                        v-validate="'required|max:35'"
                        :counter="35"
                        :error-messages="errors.collect('name')"
                        label="Name"
                        data-vv-name="name"
                        required
                    ></v-text-field>
                    <v-text-field
                    v-model="email"
                    v-validate="'required|email'"
                    :rules="[rules.email]"
                    :error-messages="errors.collect('email')"
                    label="E-mail"
                    data-vv-name="email"
                    required
                    ></v-text-field>
                    <v-textarea
                    v-model="message"
                    v-validate="'required|message'"
                    :error-messages="errors.collect('message')"
                    auto-grow
                    box
                    class="form-message"
                    label="Message"
                    data-vv-name="message"
                    rows="3"
                    required
                    ></v-textarea>
                </v-form>
                <v-btn class="grey--text text--darken-3" @click="clear">Clear</v-btn>
                <v-btn
                    :disabled="!form"
                    :loading="isLoading"
                    class="white--text"
                    color="deep-purple darken-1"
                    depressed
                    @click="submit"
                >Submit</v-btn>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<style scoped>
    .form-message {
        margin-top: 5px;
    }
</style>
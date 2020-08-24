<template>
  <section class="section-contact__wrapper pa-10" id="section-contact">
    <v-container>
      <v-row justify="center">
        <h1 class="text-h1 mb-10" uppercased>Contact</h1>
      </v-row>
      <v-row justify="center">
        <v-col cols="6" class="text-center text-subtitle-1">
          <p>
            If you found our cooperation could be successful feel free to
            contact me directly via e-mail, phone or using contact form
            below.
          </p>
        </v-col>
      </v-row>
      <v-row justify="center">
        <v-col cols="10" md="5">
          <v-card outlined class="section-contact__contact-card mb-3">
            <v-card-title>
              <span>Jarosław Bober</span>
            </v-card-title>
            <v-list color="#169873">
              <v-list-item>
                <span class="section-contact__contact-card--item font-weight-medium">535 385 005</span>
              </v-list-item>
              <v-list-item>
                <span class="section-contact__contact-card--item font-weight-medium">jarek.bober@gmail.com</span>
              </v-list-item>
            </v-list>
          </v-card>
        </v-col>
        <v-spacer width="100" class="d-none d-md-flex"></v-spacer>
        <v-col cols="10" md="5">
          <v-form
            action="https://formspree.io/jarek.bober@gmail.com"
            method="POST"
            @submit.prevent="sendEmail"
          >
            <v-text-field 
              label="Name"
              color="#14213d"
              class="input-field"
              outlined
              v-model="nameContact"
              :rules="nameRules"
            >
            </v-text-field>
            <v-text-field
              label="E-mail"
              type="email"
              name="_replyto"
              color="#14213d"
              outlined
              v-model="mailContact"
              :rules="emailRules"
            >
            </v-text-field>
            <v-textarea
              label="Text"
              name="message"
              color="#14213d"
              outlined
              v-model="messageContact"
              :rules="textRules"
            >
            </v-textarea>
            <div class="d-flex justify-space-between">
              <v-btn
                type="submit"
                :loading="isSending"
                :disabled="!nameContact || !mailContact || !messageContact"
              >
                send
              </v-btn>
              <v-alert
                dense
                outlined
                color="white"
                type="success"
                v-if="formSent"
              >
                Message sent.
              </v-alert>
            </div>
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
import axios from "axios";

export default {
  name: "SectionContact",
  data: function() {
    return {
      nameContact: "",
      mailContact: "",
      messageContact: "",
      isSending: false,
      formSent: false,
      nameRules: [
        v => !!v || 'Name is required',
      ],
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..{2,4}/.test(v) || 'E-mail must be valid',
      ],
      textRules: [
        v => !!v || 'Text is required',
      ]
    };
  },
  methods: {
    sendEmail() {
      this.isSending = true;
      axios
        .post("https://formspree.io/jarek.bober@gmail.com", {
          name: this.nameContact,
          from: this.mailContact,
          _subject: `${this.nameContact} | Message from portfolio`,
          message: this.messageContact
        })
        .then((response) => {
          this.isSending = false,
          this.formSent = true,
            console.log(response);
        })
        .catch((error) => {
          if(error.response) {          
          // eslint-disable-next-line no-alert          
          alert(error.response.data);
          }
        });
    }
  }
};
</script>

<style lang="scss" scoped>
.section-contact__wrapper {
  background-color: #169873;
  color: #14213d;
}

.section-contact__contact-card {
  color: #169873;
  background-color: #14213d;
  border: 1px solid #14213d;
}

.section-contact__contact-card--item {
  color: #14213d;
}
</style>

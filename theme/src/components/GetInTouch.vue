<template>
  <section
    id="get-in-touch"
    class="overflow-hidden"
  >
    <v-row
      class="info white--text"
      no-gutters
    >
      <v-col
        class="hidden-sm-and-down"
        md="6"
      >
        <v-img
          :src="require('@/assets/contact.png')"
          height="100%"
        />
      </v-col>

      <v-col
        class="pa-5"
        cols="12"
        md="6"
      >
        <base-bubble-1 />

        <base-heading class="mb-5">
          Get In Touch
        </base-heading>

        <v-sheet
          color="transparent"
          max-width="600"
        >
          <v-text-field
            v-model="name"
            color="info"
            label="Name"
            solo
            flat
          />

          <v-text-field
            v-model="email"
            color="info"
            :rules="emailRules"
            label="Email"
            solo
            flat
          />

          <v-text-field
            v-model="subject"
            color="info"
            label="Subject"
            solo
            flat
          />

          <v-textarea
            v-model="message"
            color="info"
            label="Message"
            solo
            flat
          />

          <base-btn
            @click.prevent="sendEmail()"
          >
            Send
          </base-btn>
          <v-snackbar
            v-model="snackbar"
            :timeout="timeout"
          >
            {{ text }}

            <template v-slot:action="{ attrs }">
              <v-btn
                color="blue"
                text
                v-bind="attrs"
                @click.prevent="snackbar = false"
              >
                Close
              </v-btn>
            </template>
          </v-snackbar>
        </v-sheet>
      </v-col>
    </v-row>
  </section>
</template>

<script>
  import emailJs from 'emailjs-com'
  export default {
    name: 'GetInTouch',

    data: () => {
      return {
        email: '',
        name: '',
        subject: '',
        message: '',
        snackbar: false,
        timeout: 2000,
        text: '',
        emailRules: [
          v => !!v || 'E-mail is required',
          v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
        ],
        nameRules: [
          v => !!v || 'Name is required',
        ],
        subjectRules: [
          v => !!v || 'Subject is required',
        ],
        messageRules: [
          v => !!v || 'Message is required',
        ],
      }
    },

    methods: {
      sendEmail () {
        let status = true
        if (!this.email || !this.name || !this.subject || !this.message) {
          this.text = 'All field is required'
          this.snackbar = true
          status = false
        }
        if (status) {
          const templateParams = {
            reply_to: this.email,
            from_name: this.name,
            subject: this.subject,
            message_html: this.message,
          }
          const serviceId = 'gmail'
          const templateId = 'template_fm0eMWmZ'
          emailJs.send(serviceId, templateId, templateParams, 'user_DdthUUHUL6q47JnvKiK3D')
            .then(data => {
              this.snackbar = true
              this.text = 'Succes! I\'ll reply your message as soon as possible'
              this.email = ''
              this.subject = ''
              this.message = ''
              this.name = ''
            })
            .catch(err => {
              this.snackbar = true
              this.text = err.text
            })
        }
      },
    },
  }
</script>

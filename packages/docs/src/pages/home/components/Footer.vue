<template>
  <v-footer
    id="footer"
    class="justify-center align-center py-4"
    color="grey darken-4"
    dark
    height="auto"
  >
    <v-container>
      <v-layout wrap>
        <v-flex xs12>
          <h5 class="mb-3">
            <v-layout
              align-center
              column
              justify-center
            >
              <v-img
                contain
                height="64px"
                src="https://cdn.vuetifyjs.com/images/logos/v-alt.svg"
                width="64px"
              />
            </v-layout>
          </h5>
        </v-flex>
        <v-flex xs12>
          <v-layout justify-center mb-3>
            <a
              v-for="(social, i) in socials"
              :key="i"
              :href="social.href"
              :title="social.title"
              class="mx-3"
              target="_blank"
              rel="noopener"
            >
              <v-icon
                dark
                v-text="social.icon"
              />
            </a>
          </v-layout>
        </v-flex>
        <v-flex
          xs12
          sm8
          md5
          mx-auto
        >
          <v-form
            action="https://www.getrevue.co/profile/vuetify/add_subscriber"
            method="post"
            name="revue-form"
            target="_blank"
          >
            <v-text-field
              id="member_email"
              v-model="email"
              class="v-text-field--rounded"
              color="secondary"
              type="email"
              name="member[email]"
              solo
              flat
              hide-details
              label="Email Address"
            >
              <template v-slot:append>
                <v-btn
                  type="submit"
                  color="secondary"
                  name="member[subscribe]"
                  value="Subscribe"
                  @click="email = ''"
                >
                  Subscribe
                </v-btn>
              </template>
            </v-text-field>
          </v-form>
          <div class="text-xs-center caption">
            Subscribe to our <strong>monthly</strong> Newsletter
          </div>
        </v-flex>
        <v-flex xs12 />
        <v-flex
          xs12
          my-5
          text-xs-center
        >
          <v-divider
            class="mx-auto"
            style="width: 150px; max-width: 70%;"
          />
        </v-flex>
        <v-flex xs12>
          <v-layout
            column
            text-xs-center
          >
            <div>
              Released under the&nbsp;
              <a
                href="https://opensource.org/licenses/MIT"
                class="grey--text text--lighten-1"
                rel="noopener"
                target="_blank"
              >
                MIT License
              </a>
              <div class="mb-3">
                Copyright &copy; 2016-{{ (new Date()).getFullYear() }} Vuetify, LLC
              </div>
              <a
                class="grey--text text--lighten-1"
                target="_blank"
                rel="noopener"
                href="https://www.iubenda.com/privacy-policy/76325752"
              >
                Privacy Policy
              </a>
              &nbsp;•&nbsp;
              <a
                class="grey--text text--lighten-1"
                target="_blank"
                rel="noopener"
                href="https://www.iubenda.com/privacy-policy/76325752/cookie-policy"
              >
                Cookie Policy
              </a>
            </div>
          </v-layout>
        </v-flex>
      </v-layout>
    </v-container>
  </v-footer>
</template>

<script>
  export default {
    data: () => ({
      email: '',
      socials: [
        {
          icon: 'mdi-reddit',
          href: 'https://www.reddit.com/r/vuetifyjs',
          title: 'Reddit'
        },
        {
          icon: 'mdi-medium',
          href: 'https://medium.com/vuetify',
          title: 'Medium'
        },
        {
          icon: 'mdi-github-circle',
          href: 'https://github.com/vuetifyjs/vuetify',
          title: 'Github'
        },
        {
          icon: 'mdi-twitter',
          href: 'https://twitter.com/vuetifyjs',
          title: 'Twitter'
        },
        {
          icon: 'mdi-facebook',
          href: 'https://www.facebook.com/vuetifyjs',
          title: 'Facebook'
        },
        {
          icon: 'mdi-discord',
          href: 'https://community.vuetifyjs.com',
          title: 'Discord Community'
        }
      ]
    })
  }
</script>

<style lang="stylus">
  #footer
    a
      opacity: .8
      text-decoration: none

      &:hover
        color: #FFF
        opacity: 1

    .v-text-field--rounded
      margin-bottom: 16px

      .v-input__slot
        border-radius: 28px

      .v-text-field__slot,
      .v-label
        padding-left: 8px

      .v-btn
        margin: 0
        border-top-right-radius: 28px
        border-bottom-right-radius: 28px
        box-shadow: none
        height: 48px
        margin-right: -12px
        padding-top: 2px
</style>

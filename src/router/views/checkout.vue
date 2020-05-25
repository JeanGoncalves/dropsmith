<script>
import Layout from '@layouts/main.vue'

export default {
  page: {
    title: 'Checkout',
    meta: [{ name: 'description', content: 'The Checkout page.' }],
  },
  components: { Layout },
  data() {
    return {
      firstName: '',
      lastName: '',
      mail: '',
      password: '',
      subscription: '',
      couponCode: '',
      payment: {
        cardNumber: '',
        cardValidate: '',
        cardCVC: '',
      },
      acceptTerms: false,
      acceptNewsletter: false,
      checked: '',
    }
  },
  methods: {
    handleChecked(value) {
      this.checked = value
    },
  },
}
</script>

<template>
  <Layout :has-navbar="'false'">
    <img src="@assets/images/dropsmith-logo.png" alt="Logo" />
    <h2>Join the global aromatherapy movement</h2>

    <div :class="$style.content">
      <!-- Description -->
      <section :class="$style.description">
        <ul>
          <li><BaseIcon name="tint" />Browse's profiles</li>
          <li><BaseIcon name="tint" />Browse basic essential oil data</li>
          <li><BaseIcon name="tint" />Browse blends of other users</li>
          <li><BaseIcon name="tint" />Browse the active community</li>
          <li><BaseIcon name="tint" />View detailed reports</li>
          <li><BaseIcon name="tint" />Compare essential oils</li>
          <li><BaseIcon name="tint" />Create blends</li>
          <li><BaseIcon name="tint" />Publish and share your blends</li>
          <li><BaseIcon name="tint" />Comment on blends in thecommunity</li>
          <li><BaseIcon name="tint" />Create you own workspace</li>
          <li><BaseIcon name="tint" />Print your essential oils and blends</li>
        </ul>
      </section>

      <!-- Form -->
      <section :class="$style.form">
        <form>
          <h2>Sign Up</h2>

          <!-- First Name Input -->
          <BaseInputText
            v-model="firstName"
            name="firstName"
            aria-placeholder="First Name"
            placeholder="First Name"
          />

          <!-- Last Name Input -->
          <BaseInputText
            v-model="lastName"
            name="lastName"
            aria-placeholder="Last Name"
            placeholder="Last Name"
          />

          <!-- E-mail Input -->
          <BaseInputText
            v-model="mail"
            name="mail"
            aria-placeholder="E-mail"
            placeholder="E-mail"
          />

          <!-- Password Input -->
          <BaseInputText
            v-model="password"
            name="password"
            aria-placeholder="Password"
            placeholder="Password"
          />

          <!-- Subscription Radio Input -->
          <BaseInputRadio
            :name="'add_to_cart'"
            :labels="[
              {
                value: '392',
                id: 'product_392',
                title: 'Monthly Subscription',
                subtitle: '19€ / month',
              },
              {
                value: '393',
                id: 'product_393',
                title: 'Yearly Subscription',
                subtitle: '197€ / year',
                detail: 'Recommended - 14% Off',
              },
            ]"
            @callback="handleChecked"
          />
          <!-- handleChecked: {{ checked }} -->

          <!-- Card Info Subscription -->
          <BaseCardInfo
            :title="'19€ / month'"
            :description="'First renewal: 25/06/2020'"
            :info="'With 30-day money back guarantee'"
          />

          <h2>Payment</h2>
          <p>Debit/Credit</p>

          <!-- Payment Card Number Input -->
          <BaseInputText
            v-model="payment.cardNumber"
            name="paymentCardNumber"
            aria-placeholder="1234 1234 1234 1234"
            placeholder="1234 1234 1234 1234"
            type="number"
          />

          <div :class="$style.twoColumn">
            <!-- Payment Validate Input -->
            <BaseInputText
              v-model="payment.cardValidate"
              name="paymentCardValidate"
              aria-placeholder="MM / AA"
              placeholder="MM / AA"
            />

            <!-- Payment CVC Input -->
            <BaseInputText
              v-model="payment.cardCVC"
              name="paymentCardCVC"
              aria-placeholder="CVC"
              placeholder="CVC"
              type="number"
            />
          </div>

          <!-- Image Secure SSL Encryption -->
          <img
            src="@assets/images/ssl-30days.jpg"
            alt="Secure SSL Encryption"
          />

          <!-- Terms and Conditions accept -->
          <BaseInputCheckbox
            id="acceptTerms"
            v-model="acceptTerms"
            name="acceptTerms"
          >
            I agree to Dropsmith's <a href="#">terms and conditions</a> *
          </BaseInputCheckbox>

          <!-- Newsletter accept -->
          <BaseInputCheckbox
            id="acceptNewsletter"
            v-model="acceptNewsletter"
            name="acceptNewsletter"
          >
            I want to stay informed by Dropsmith newsletter
          </BaseInputCheckbox>

          <p>
            We follow the GDPR rules and the information you provide here will
            only be used to share with you Dropsmith's updates and special
            marketing offers. You can unsubscribe at any time!
          </p>

          <BaseButton>
            Give me instant access!
          </BaseButton>

          <div>
            <b>Got a Question? Contact Us!</b>
            <p>support@dropsmith.com</p>
          </div>
        </form>
      </section>
    </div>
  </Layout>
</template>

<style lang="scss" module>
@import '@design';

.content {
  display: flex;
  justify-content: space-between;

  > section {
    width: 100%;
    padding: $size-grid-padding * 2.3;
    margin: 0 15px;
  }
}

.twoColumn {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 20px;
}

.description {
  ul {
    list-style: none;
  }
}

.form {
  border: 1px solid #aaa;
}
</style>

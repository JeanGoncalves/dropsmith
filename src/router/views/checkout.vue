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
      newsletter: false,
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
      <div :class="$style.description">column 1</div>
      <div :class="$style.form">
        Sign Up
        <form>
          <BaseInputText
            v-model="firstName"
            name="firstName"
            aria-placeholder="First Name"
            placeholder="First Name"
          />

          <BaseInputText
            v-model="lastName"
            name="lastName"
            aria-placeholder="Last Name"
            placeholder="Last Name"
          />

          <BaseInputText
            v-model="mail"
            name="mail"
            aria-placeholder="E-mail"
            placeholder="E-mail"
          />

          <BaseInputText
            v-model="password"
            name="password"
            aria-placeholder="Password"
            placeholder="Password"
          />

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
        </form>
        handleChecked: {{ checked }}
      </div>
    </div>
  </Layout>
</template>

<style lang="scss" module>
@import '@design';

.content {
  display: flex;
  justify-content: space-between;

  > div {
    width: 100%;
    padding: $size-grid-padding * 2.3;
    margin: 0 15px;
  }
}

.description {
  background-color: blue;
}

.form {
  border: 1px solid #aaa;
}
</style>

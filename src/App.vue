<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Welcome to Rave VueJS SDK</h1>
    <rave :email="email"
          :amount="amount"
          :reference="reference"
          :rave-key="raveKey"
          :callback="callback"
          :close="close"
          :currency="currency"
          :country="country"
          :customer_firstname="customer.firstname"
          :customer_lastname="customer.lastname"
          :custom_title="custom.title"
          :custom_description="custom.description"
          :custom_logo="custom.logo"
          :redirect_url="redirectUrl"
          :payment_plan="paymentPlan"
          :subaccounts="subaccounts"
          :payment_method="paymentMethod"/>
  </div>
</template>

<script>
import Rave from './components/rave-modal.vue'

export default {
  name: 'app',
  components: {
    Rave
  },
  data(){
    return{
      //you can set all values you want to pass and initialize it in the template above
      raveKey: "FLWPUBK-56e4a2c6c9a6b58364bfd07fc1993e2c-X", // replace with your key from your dashboard
      email: "test@example.com", // email address of your client
      amount: 1,  // replace with your desired amount
      currency: "NGN", // supported currencies NGN, USD, EUR, GBP UGX, TZX, GHS, KES, ZAR
      country: "NG", // pass country NG, GH, KE, ZA 
      customer: {
        firstname: "", // add customer firstname
        lastname: "" // add customer lastname
      },
      custom: {
        title: "", // add custom title
        description: "", // add a description
        logo: "" // add logo
      },
      redirectUrl: "", // add redirect url
      paymentPlan: "", // add payments plan ID here
      paymentMethod: "", // add 'card' or 'account' if you want a specific feature. Leave empty if you want all features
      subaccounts: {
        id: "RS_73954F005E68DADF3483197D5CF13E1E", // id of the subaccount; get from your dashboard
        transaction_split_ratio:"", //
        transaction_charge_type: "", //include this if the you want a flat fee eg: flat
        transaction_charge: "" // include the flat fee amount you want eg: 100
      } // add a subaccount for split payments
    }
  },
  computed: {
    reference(){
      let text = "";
      let possible = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";

      for( let i=0; i < 10; i++ )
        text += possible.charAt(Math.floor(Math.random() * possible.length));

      return text;
    }
  },
  methods: {
    callback: function(response){
      console.log(response)
    },
    close: function(){
      console.log("Payment closed")
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

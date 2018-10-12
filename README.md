# Vue-Rave Plugin

======================================

### Project Setup
1. clone the repo to your desktop by running the code `git clone https://github.com/emmajiugo/rave-vue.git` on your CMD
2. cd into the project folder
3. Run `npm install` to install all dependencies
4. Compile and Hot-reload for developement
    ```
        npm run serve
    ```
5. By default, your project should be running on `port: 8080`. Go to your browser and type `localhost:8080` to start your project testing.

### Features Included
- Card Payment
- Account Payment
- Payment Plan (i.e. for subscription)
- Subaccount (i.e. for split payments)

### How To Use
After setting up the project on your computer, open the `App.vue` file from your **src** folder and add your credentials and details as necessary.

##### Sample code for editting on the App.vue file
```javascript
    //you can set all values you want to pass
    raveKey: "FLWPUBK-XXXXXX-X", // replace with your key from your dashboard
    email: "test@example.com", // email address of your client
    amount: 10,  // replace with your desired amount
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
    id: "RS_XXXXXXXX", // id of the subaccount; get from your dashboard
    transaction_split_ratio:"", //
    transaction_charge_type: "", //include this if the you want a flat fee eg: flat
    transaction_charge: "" // include the flat fee amount you want eg: 100
    } // add a subaccount for split payments
```

You can set all the values you want to pass to the above code to run your test.

To get your Rave's `Public-key` and `Secret-Key`, visit and signup on `https://ravesandbox.flutterwave.com/` for test keys, while for your live keys, visit and signup on `https://rave.flutterwave.com/`

To go live, make sure your live keys are used and open `rave-modal.vue` from your `component folder` and set the `isProduction` default to `true`.
```javascript
    isProduction: {
        type: Boolean,
        required: false,
        default: false //set to true if you are going live
    },
```

Thankyu!!!

Chigbo Ezejiugo (HRH Emmajiugo)

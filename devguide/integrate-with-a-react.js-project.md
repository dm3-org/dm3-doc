# Integrate with a React.js project

## Getting Started

This guide will help you integrate the DM3 widget component into your frontend applications effectively.

## Overview

The DM3 widget is an UI component designed for integration into your frontend applications to enable messaging functionality. Messaging is essential for various dApps, such as wallets, trading platforms, games, and social media apps, as it supports in-app communication, customer support, and contact management.

## Integrate with a React.js project

Follow these steps to ensure proper setup and configuration:

### **Step 1: Create a new React.js project or use an existing project**

&#x20;Create a new React.js project with typescript:

{% tabs %}
{% tab title="yarn" %}
```bash
yarn create react-app dm3-app --template typescript
```
{% endtab %}

{% tab title="npm" %}
```bash
npx create-react-app dm3-app --template typescript
```
{% endtab %}
{% endtabs %}

Create a new React.js project:



{% tabs %}
{% tab title="yarn" %}
```bash
yarn create react-app dm3-app
```
{% endtab %}

{% tab title="npm" %}
```bash
npx create-react-app dm3-app
```
{% endtab %}
{% endtabs %}

Or, use an existing project:

```bash
cd  /existing_project_path
```

### **Step 2: Navigate to the dm3-app directory:** (Skip this step if you're using an existing project)

```bash
cd dm3-app
```

### **Step 3: Install dm3-messenger widget:**&#x20;

{% tabs %}
{% tab title="yarn" %}
{% code overflow="wrap" fullWidth="true" %}
```bash
yarn add @dm3-org/dm3-messenger-widget
```
{% endcode %}
{% endtab %}

{% tab title="npm" %}
```bash
 npm install @dm3-org/dm3-messenger-widget
```
{% endtab %}
{% endtabs %}

### **Step 4: Create a .env file at the root level of your app or project:**

```bash
 touch .env
```

### **Step 5: Copy the below content and paste it into the .env file:**

{% tabs %}
{% tab title="Sepolia Testnet" %}
```properties
REACT_APP_ADDR_ENS_SUBDOMAIN=.beta-addr.dm3.eth
REACT_APP_BACKEND=https://staging.dm3.network/api
REACT_APP_DEFAULT_DELIVERY_SERVICE=beta-ds.dm3.eth
REACT_APP_DEFAULT_SERVICE=https://staging.dm3.network/api
REACT_APP_MAINNET_PROVIDER_RPC=https://eth-sepolia.g.alchemy.com/v2/<alchemy-key>
REACT_APP_PROFILE_BASE_URL=https://staging.dm3.network/api
REACT_APP_RESOLVER_BACKEND=https://staging.dm3.network/resolver-handler
REACT_APP_USER_ENS_SUBDOMAIN=.beta-user.dm3.eth
REACT_APP_WALLET_CONNECT_PROJECT_ID=27b3e102adae76b4d4902a035da435e7
REACT_APP_CHAIN_ID=11155111
REACT_APP_PUBLIC_VAPID_KEY=BFCJLre0GeM6S-n4mkMX4SLZWlDR9qc8RsHyctsOPh_QDQkBuvCrMe9Rmq24736F-CJFp-3DkDWhp19X7mOJrEc
REACT_APP_NONCE=0x12345fe712345
```
{% endtab %}

{% tab title="Ethereum Mainnet" %}
```properties
REACT_APP_ADDR_ENS_SUBDOMAIN=.addr.dm3.eth
REACT_APP_USER_ENS_SUBDOMAIN=.user.dm3.eth
REACT_APP_BACKEND=https://app.dm3.network/api
REACT_APP_DEFAULT_DELIVERY_SERVICE=ds.dm3.eth
REACT_APP_DEFAULT_SERVICE=https://app.dm3.network/api
REACT_APP_PROFILE_BASE_URL=https://app.dm3.network/api
REACT_APP_RESOLVER_BACKEND=https://app.dm3.network/resolver-handler
REACT_APP_WALLET_CONNECT_PROJECT_ID=27b3e102adae76b4d4902a035da435e7
REACT_APP_MAINNET_PROVIDER_RPC=https://eth-mainnet.g.alchemy.com/v2/<alchemy-key>
REACT_APP_CHAIN_ID=1
REACT_APP_PUBLIC_VAPID_KEY=BFCJLre0GeM6S-n4mkMX4SLZWlDR9qc8RsHyctsOPh_QDQkBuvCrMe9Rmq24736F-CJFp-3DkDWhp19X7mOJrEc
REACT_APP_NONCE=0x12345fe712345
```
{% endtab %}
{% endtabs %}

**Note**: Replace `<alchemy-key>` of `REACT_APP_MAINNET_PROVIDER_RPC`with your actual key and `<REACT_APP_NONCE>` with some unique hexadecimal string. For better security, ensure the nonce is longer than 20 characters.

### **Step 6: Configure the DM3 widget:**

In the <mark style="color:blue;">src/App.tsx</mark> file or in any component where you want to use the DM3 widget,  import and configure it as follows:

```jsx
import { DM3, DM3Configuration } from '@dm3-org/dm3-messenger-widget';

 function MyComponent() {

     const props: DM3Configuration = {
         userEnsSubdomain: process.env.REACT_APP_USER_ENS_SUBDOMAIN as string,
         addressEnsSubdomain: process.env.REACT_APP_ADDR_ENS_SUBDOMAIN as string,
         resolverBackendUrl: process.env.REACT_APP_RESOLVER_BACKEND as string,
         profileBaseUrl: process.env.REACT_APP_PROFILE_BASE_URL as string,
         defaultDeliveryService: process.env.REACT_APP_DEFAULT_DELIVERY_SERVICE as string,
         backendUrl: process.env.REACT_APP_BACKEND as string,
         chainId: process.env.REACT_APP_CHAIN_ID as string,
         defaultServiceUrl: process.env.REACT_APP_DEFAULT_SERVICE as string,
         ethereumProvider: process.env.REACT_APP_MAINNET_PROVIDER_RPC as string,
         walletConnectProjectId: process.env.REACT_APP_WALLET_CONNECT_PROJECT_ID as string,
         publicVapidKey: process.env.REACT_APP_PUBLIC_VAPID_KEY as string,
         nonce: process.env.REACT_APP_NONCE as string,
         defaultContact: 'help.dm3.eth',
         showAlways: true,
         hideFunction: undefined, 
         showContacts: true,
         theme: undefined, 
         signInImage: undefined,
         siwe: undefined
     };

     return (
         <div className="dm3-container">
             <DM3 {...props} />
         </div>
     );
 }

 export default MyComponent;
```



### **Step 7: Add the following style in **<mark style="color:blue;">**App.css**</mark>** file:**

This style will be applied to the `.dm3-container`.

```css
.dm3-container {
    border-radius: 25px;  /* Optional property */
    overflow: hidden;  /* Optional property only if wanted to set border radius */
    height: 100vh; /* If the container has no height, then it is mandatory to set some height*/
    width: 100vw; /* If the container has no width, then it is mandatory to set some width */
}

```

### **Step 8: Start the project by running the following command in terminal:**

{% tabs %}
{% tab title="yarn" %}
```bash
yarn start
```
{% endtab %}

{% tab title="npm" %}
```bash
npm start
```
{% endtab %}
{% endtabs %}

## Widget Props Customization

These are properties of the widget that can be customized to suit your needs, allowing you to change its appearance, and functionality as desired.

1. **nonce** \
   \
   This is a mandatory property. This is a nonce value used as a key in storage. It must be unique for each client and should be in hexadecimal format. For better security, opt for a nonce that is longer than 20 characters.\
   For generating hexadecimal value, you can use this [<mark style="color:blue;">website</mark>](https://codebeautify.org/generate-random-hexadecimal-numbers).\
   \
   **Important** - It is essential that the nonce remains unchanged to prevent users from losing access to their messages.

```jsx
const props: DM3Configuration = {
   ...
   nonce: '0x12e05caefa498a611ecc0',
}
```



```jsx
Example:
nonce: '0x25bcf02bba90ebd97c4b91'
nonce: '0x9123d63a91744bc6c843768e21'
```

2. **defaultContact** \
   \
   This is a mandatory property. The default ENS name for the contact will automatically be added to the contact list when the widget is used, so there's no need to add the contact manually.

```jsx
const props: DM3Configuration = {
   ...
   defaultContact: 'help.dm3.eth',
}
```

```jsx
Example: 
   defaultContact: 'help.dm3.eth'
   defaultContact: '0x71C7656EC7ab88b098defB751B7401B5f6d8976F.dm3.eth'
```

3.  **hideFunction**

    \
    This is an optional property. By default, it is <mark style="color:blue;">`undefined`</mark>. Users can use it to hide specific functionalities within the widget, such as <mark style="color:blue;">attachments</mark>, <mark style="color:blue;">edit</mark>, and <mark style="color:blue;">delete</mark>. Multiple functionalities can be hidden by setting them as a comma-separated list.

```jsx
const props: DM3Configuration = {
   ...
   hideFunction: 'attachments',
}
```

```jsx
Example: 
   hideFunction: 'attachments'
   hideFunction: 'edit'
   hideFunction: 'delete'
   hideFunction: 'edit,delete'
   hideFunction: 'attachments,edit,delete'
   hideFunction: undefined
```

4. **showContacts**\
   \
   This is a mandatory property of type <mark style="color:blue;">`boolean`</mark>. The value <mark style="color:blue;">`true`</mark> enables the widget to show entire contacts list and many contacts can be added in the list dynamically. The value <mark style="color:blue;">`false`</mark> represents only the default contact is active and chatting can be done with that contact only.

```jsx
const props: DM3Configuration = {
   ...
   showContacts: true,
}
```

```jsx
Example: 
   showContacts: true
   showContacts: false
```

5.  **signInImage**

    \
    This is an optional property of type <mark style="color:blue;">`string`</mark>. You can set it to either a base64-encoded image URL or a web URL of an image. This image will be displayed on the sign in screen of the widget.\


```jsx
const props: DM3Configuration = {
   ...
   signInImage: "https://myimage.png",
}
```

```jsx
Example: 
   signInImage: undefined
   signInImage: "https://letsenhance.io/static/8f5e523ee6b2479e26ecc91b9c25261e/1015f/MainAfter.jpg"
```

6. **siwe**\
   \
   This is an optional property of type <mark style="color:blue;">`object`</mark>. Using this one can sign in into DM3 with the SIWE (Sign In With Ethereum). All the properties of the object are mandatory.

```jsx
const props: DM3Configuration = {
   ...
   siwe: {
        address: "0xe7861D923e1B055bB25CD49569d20903c44692c5",
        message: "my msg",
        signature: '0xc9c8df80009a302559642d67adeea12d6e3f2ecbd7702986596b4012a5f5956e70c2a2c658f7c02e9255499049ea518fdf714cadc121b0319aee80f7ae28b0181b',
        secret: "my-super-secret0"
    }
}
```

```jsx
Example: 
   siwe: undefined
   siwe: {
        address: "0xe7861D923e1B055bB25CD49569d20903c44692c5",
        message: "my msg",
        signature: '0xc9c8df80009a302559642d67adeea12d6e3f2ecbd7702986596b4012a5f5956e70c2a2c658f7c02e9255499049ea518fdf714cadc121b0319aee80f7ae28b0181b',
        secret: "my-super-secret0"
    }
```

**Address:**

The address of the user's wallet.

**Message:**

The login message. This can be any SIWE-like message. This message might not be confidential and also could contain a timestamp.

**Signature:**

The signature to the above message.\
\
For generating the signature, you may use this[ ](https://etherscan.io/verifiedSignature)[website](https://etherscan.io/verifiedSignatures).

**Secret:**

A unique secret identifier this value is the secret entropy to be used as a seed for the internal keys to be derived from. It must not be shared anywhere else. Also, the embedding app is responsible for storing this securely, as it is "the key" for the communication. For instance, this could be a derivation, signature,... from an internally used private key. Important the embedding app is responsible for security, recovery, etc.

7. **theme**\
   \
   This is an optional object property that allows you to customize the widget's styling, appearance, and overall look and feel. You can specify custom colors for different components, such as the background, text, buttons, and borders, to match your application's theme. By default, the DM3 widget uses a <mark style="color:blue;">dark theme</mark>, but you can easily modify it to fit your preferred color scheme.

```jsx
const props: DM3Configuration = {
   ...
   theme: undefined,
}
```

The following example demonstrates the widget with a <mark style="color:blue;">light theme.</mark>

```jsx
Example : 
   theme: undefined
   theme: {
    backgroundColor: '#f5f5f5',
    buttonBorderColor: '#d0d0d0', 
    configBoxBorderColor: '#a0a0a0',
    buttonColor: '#c0a080', 
    hoverButtonColor: '#c0a080',
    inactiveButtonColor: '#d0d0d0', 
    inactiveButtonTextColor: 'black', 
    primaryTextColor: 'black', 
    secondaryTextColor: '#666666', 
    activeContactBackgroundColor: '#c0a080',  
    configurationBoxBackgroundColor: '##d8d5d5',
    configurationBoxBorderColor: '#d0d0d0',
    chatBackgroundColor: '#f0f0f0',
    disabledButtonTextColor: 'black', 
    errorTextColor: '#c00', 
    errorBackgroundColor: '#fdd', 
    attachmentBackgroundColor: '#d0d0d0', 
    selectedContactBorderColor: '#aa8d51',
    profileConfigurationTextColor: '#666666',
    receivedMessageBackgroundColor: '#e6f7ff', 
    receivedMessageTextColor: '#003366', 
    sentMessageBackgroundColor: '#cce5ff',
    sentMessageTextColor: '#003366', 
    infoBoxBackgroundColor: '#e3e6eb', 
    infoBoxTextColor: 'black',
    buttonShadow: '##d6cfcf', 
    msgCounterBackgroundColor: '#ffeb3b', 
    msgCounterTextColor: '#000000', 
    scrollbarBackgroundColor: '#d0d0d0', 
    scrollbarScrollerColor: '#a0a0a0', 
    inputFieldBackgroundColor: '#ffffff',
    inputFieldTextColor: '#000000',
    inputFieldBorderColor: '#d0d0d0', 
    emojiModalBackgroundColor: '240, 248, 255', 
    emojiModalTextColor: '102, 51, 153',
    emojiModalAccentColor: '255, 105, 180', 
    rainbowConnectBtnBackgroundColor: '#007bff', 
    rainbowConnectBtnTextColor: '#ffffff',
    rainbowAccentColor: '#ff9800',
    rainbowAccentForegroundColor: '#ffb6c1',
    rainbowModalTextColor: '#ffffff',
    rainbowModalTextSecondaryColor: '#ffff00', 
    rainbowModalWalletHoverColor: 'c0a080',
    rainbowModalBackgroundColor: '#007bff',
    alternateContactBackgroundColor: '#ffffff', 
    menuBackgroundColor: '#fffbfb',
    preferencesHighlightedColor: '#88633f',
   }
```

**NOTE**&#x20;

All other properties are required and cannot be customized. They must match the values specified in the `.env` configuration.

\

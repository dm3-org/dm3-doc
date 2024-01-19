# Registry

A central (but decentralized) registry is needed where a **dm3** compatible app, service, or protocol can lookup **dm3 profiles** of other users, containing

* Public keys,
* Links to delivery services.

The **dm3** protocol uses **ENS (Ethereum Name Service)** as a central (but decentralized) registry. The following text records are used for this purpose:

* `network.dm3.profile`: User profile entry
* `network.dm3.deliveryService`: Delivery service profile entry

The text records MUST be a URI containing the profile JSON string defined below.

The URI can be

* A data scheme (_data:..._) or
* A URL pointing to a profile JSON object (_HTTPS:... or IPFS:..._). To validate the integrity of the resolved profile JSON string, the URL MUST be a native IPFS URL or a URL containing a `dm3Hash` parameter containing the **SHA-256** hash of the JSON.

> **Example** `network.dm3.profile` text record entries:
>
> * `data:application/json,{profile...`
> * `https://delivery.dm3.network/profile/0xbcd6de065fd7...b3cc?dm3Hash=ab84f8...b50c8`
> * `ipfs://bafybeiemxf5abjwjz3e...vfyavhwq/`

The profiles can only be changed by creating a new profile JSON and changing the corresponding text record via an Ethereum transaction (if published on layer-1). Storing this information on layer-2 or linked via CCIP ([Cross-Chain Interoperability Protocol](https://chain.link/cross-chain)) using subdomains, is possible, too. The specification thereof will be published in the protocol extension **Layer-2 Registry Specification**. This is currently under development and will be published soon.

Information read from ENS may be cached for performance reasons but the ENS TTL settings must be respected (to be fetched from the resolver).

## User Profile

The user profile MUST contain:

* **Public Signing Key:** Key used to verify a message signature (ECDSA). The public signing key is the public key of a secp256k1 private/public key pair. How to generate or derive this key pair depends on the implementation of the client. The **Encryption and Signing Key Derivation Specification** proposes a method to derive those keys based on a signature of the wallet keys. The key is presented as base64-encoded string of the key's bytes (see [key encoding](broken-reference)).
* **Public Encryption Key:** Public key used to create the key (together with the private key of the sender) to encrypt a message. As default, the algorithm **x25519-chacha20-poly1305** is used (see **\[NIR1]**). If needed (e.g., for compatibility reasons with an integrated protocol), a different encryption can be specified in the Profile Extension. Nevertheless, using the default encryption is highly recommended. The key is presented as base64-encoded string of the key's bytes (see [key encoding](broken-reference)).
* **Delivery Service List:** List with at least one delivery service' ENS name[^1].

```JavaScript
DEFINITION: UserProfile

{
  // Key used to encrypt messages
  publicEncryptionKey: string,
  // Key used to sign messages
  publicSigningKey: string,
  // ENS name list of the delivery services e.g., delivery.dm3.eth
  deliveryServices: string[], 
}
```

> **Example** UserProfile with fallback delivery service:
>
> ```JavaScript
> {
>    "publicEncryptionKey":"nyDsUmYV4EDNCsG+pK...D=",
>    "publicSigningKey":"MBpqhsSkxevwbYEGnXX9r...c=",
>    "deliveryService": ["example_deliveryservice.eth","example_fallback-deliveryservice.eth"]
> }
> ```

Additional to the user profile, the user profile extension can be queried from the user's delivery service (see user profile extension). As this information may change and depend as well on the delivery service, it MUST be requested directly from the delivery service the message will be sent to.

### Key encoding

Public keys published in the profiles are presented as base64-encoded strings of the key's bytes.

> **Example** Key encoding
>
> ```JavaScript
> Key = [134, 57, 101, ..., 167]
> KeyString = "jjllMO...qc="
> ```

## Delivery Service Profile

The delivery service profile MUST contain:

* **Public Signing Key:** Key used to verify a postmark signature (see **UserProfile**). The key is presented as base64-encoded string of the key's bytes (see [key encoding](broken-reference)).
* **Public Encryption Key:** Public key used to create the key (together with the private key of the sender) to encrypt a message. As default, the algorithm **x25519-chacha20-poly1305** is used. The key is presented as base64-encoded string of the key's bytes (see [key encoding](broken-reference)).
* **Delivery Service URL:** URL pointing to the delivery service instance.

As the encryption algorithm for the delivery service, the default algorithm **x25519-chacha20-poly1305** is mandatory.

```JavaScript
DEFINITION: DeliveryServiceProfile

{
  // Key used to sign postmarks
  publicSigningKey: string,
  // Key used to encrypt delivery information
  publicEncryptionKey: string,
  // URL pointing to the delivery service instance
  url: string
}
```

> **Example:** DeliveryServiceProfile
>
> ```JavaScript
> {
>    "publicEncryptionKey":"nyDsUmYV4EDNCsG+pK...D=",
>    "publicSigningKey":"MBpqhsSkxevwbYEGnXX9r...c=",
>    "url": "https://example_deliveryservice"
> }
> ```

[^1]: For information, on how to adapt **dm3** for ecosystems not based on Ethereum, see appendix [Cross Chain Applications](broken-reference).

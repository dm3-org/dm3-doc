# The Core Protocol

## **Message Relay Network**

There are various approaches to implementing decentralized communication. It is important to implement an infrastructure that is not controlled by or dependent on one party (organization or company). With dm3, the infrastructure is based on a decentralized Message Relay Node Network. These relay nodes (delivery service) are independent and temporarily store messages (message cache) until they are picked up by the recipient. As soon as the messages have been retrieved and processed by the recipient, they are deleted.

Each recipient decides for themselves which relay nodes they want to be connected to and, thus, via which nodes they can be reached. They can operate their own message relay node, use the node of a specific service, or use public independent nodes. Since the relay nodes do not redistribute the messages in the network, this type of distributed network is easily scalable by adding further nodes.

The nodes can also perform other tasks, e.g., for extended privacy, or they can act as gateways to other protocols and services. In this case, the relay node would receive a message and then inject it into the other network or service. This makes them crucial building blocks for interoperability.

The message relay nodes are expressly not intended for permanently storing messages. However, clients do this locally, in a cloud service, or even in a decentralized data store, depending on requirements and implementation.

## **Communication Profile Registry**

To enable secure, encrypted, and tamper-proof communication, various public keys and information about how messages can be delivered must be published. To enable a decentralized, permissionless, and censorship-resistant architecture, the registry that publishes this information (communication profile) must be centrally accessible yet decentralized. A central service provider cannot assume this function. Web3 technology lends itself precisely to this, with a blockchain-based registry taking on this task.

Such a communication profile contains:

* **Encryption key:** public keys for end-to-end encryption
* **Signature key:** public keys for signatures
* **Delivery Information:** Information on which message relay nodes can be used to deliver the messages.

The DM3 protocol uses ENS (Ethereum Name Service) for this registry. Each ENS name (or sub-name) can hold a text record that contains the profile.

## **Cross-chain, L2s, and Cloud-Services**

Registries from other sources (be it other chains (cross-chain), L2s, Identity profiles, or even cloud services) can also be integrated via customized resolvers (via CCIP - Cross-Chain-Interoperability Protocol) and linked to a sub-name. This way, the ENS-based registry can be used as a universal registry for communication profiles, regardless of where the information is ultimately published.

## **Token-based Functions**

A special capability of Web3 technology is that values can be digitally linked, locked, or transmitted. DM3 uses this to effectively implement various functions, e.g., spam protection, and extended privacy functions.

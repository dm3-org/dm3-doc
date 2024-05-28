---
description: DM3—the Web3 Messaging Interoperability Protocol
---

# The Protocol

The DM3 protocol is a modular messaging protocol based on effectively utilized Web3 technology. It focuses on the essential needs of a decentralized, secure, and user-focused communication ecosystem. The lean core protocol can be modularized with various protocols and utility extensions. With a particular focus on interoperability, DM3 aims to both easily connect existing solutions and serve as a core protocol for new applications.

## The DM3 Message Transport Protocol

The **DM3 Message Transport Protocol** is the core protocol of DM3. The focus of this protocol is the peer-to-peer transmission of messages. To achieve DM3 interoperability, this core protocol must be implemented. Additional protocol and utility extensions complement the MTP modular. The following features are defined in the message transport protocol:

1. The decentralized message relay network for the delivery of messages
2. The communication registry for publishing the communication profiles
3. Data structures, encryption, and signatures required for secure and private communication

### **Message Relay Network**

There are various approaches to implementing decentralized communication. Implementing an infrastructure that is not controlled by or dependent on one party (organization or company) is important. With DM3, the infrastructure is based on a decentralized Message Relay Node Network. These relay nodes (delivery services) are independent and temporarily store messages (message cache) until the recipient picks them up. As soon as the messages have been retrieved and processed by the recipient, they are deleted from the network.

Each recipient decides which relay nodes they want to be connected to and, thus, via which nodes they can be reached. Users can operate their own message relay node, use the node of a specific service, or use public independent nodes. Since the relay nodes do not redistribute the messages in the network, this distributed network is easily scalable to increase the capacity by adding further nodes.

The nodes can also perform other tasks, e.g., for extended privacy or as gateways to other protocols and services. The relay node receives a message and injects it into the other network or service as a gateway. This makes those nodes crucial building blocks for interoperability.

The message relay nodes are expressly not intended for permanently storing messages. However, depending on requirements and implementation, clients do this locally, in a cloud service, or even in a decentralized data store.

### **Communication Profile Registry**

To enable secure, encrypted, and tamper-proof communication, various public keys and information about how messages can be delivered must be published. To enable a decentralized, permissionless, and censorship-resistant architecture, the registry that publishes this information (communication profile) must be centrally accessible yet decentralized. A central service provider cannot assume this function. Web3 technology lends itself precisely to this, with a blockchain-based registry taking on this task.

Such a communication profile contains:

* **Encryption key:** public key for end-to-end encryption
* **Signature key:** public key for signatures
* **Delivery Information:** Information on which message relay nodes the messages can be delivered

The DM3 protocol utilizes ENS ([Ethereum Name Service](https://ens.domains)) for this registry. Each ENS name (or sub-name) can hold a text record that contains the profile. In this way, a trustless, permissionless registry is implemented that cannot be controlled or censored by any authority.

#### **Cross-chain, L2s, and Cloud-Services**

Registries from other sources (be it other chains (cross-chain), L2s, Identity profiles, or even cloud services) can also be integrated via customized resolvers for ENS (via CCIP - [Cross-Chain-Interoperability Protocol](https://chain.link/cross-chain)) and linked to a sub-name. This way, the ENS-based registry can be used as a universal registry for communication profiles, regardless of where the information is published.

Since ENS is freely available and presents no further onboarding hurdles (especially when using CCIP), it is well-suited as a central registry. There are no restrictions regarding the integration of other data sources. This also greatly reduces the workload for applications that use DM3, as they do not have to implement multiple interfaces to different identity solutions or other registries. Once these have been integrated into ENS as a sub-name, the required information can be accessed in a standardized way.&#x20;

However, local ecosystems can easily support DM3 native without losing interoperability with other DM3 users.

## **Token-based Functions**

A special capability of Web3 technology is that values can be digitally linked, locked, or transmitted. DM3 uses this to effectively implement various functions, such as spam protection and extended privacy functions.

Therefore, the [DM3 token](../../dm3-token/token/) can enable functions in the DM3 ecosystem and its governance functions.

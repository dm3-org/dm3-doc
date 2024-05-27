---
description: DM3's main focus is to establish messaging interoperability
---

# Interoperability

Most messengers currently in use are closed ecosystems. Communication between users of different platforms is not possible because the protocols and infrastructures are not compatible or, in the past, even interoperability was actively prevented by the service providers. From the point of view of many users, interoperability is important and desirable. In addition, interoperability is essential for the freedom to choose the software used.

There are different levels of interoperability:

* **Level 1:** New messages can be transmitted from one system to another. The systems remain responsible for storing messages.
* **Level 2:** In addition to transferring new messages, it is also possible to synchronize saved conversations.
* **Level 3:** All resources can be shared (new messages, historical conversations, configurations, etc.)

Level 1 is required for an interoperable ecosystem; level 2 is useful but not essential. To support the greatest possible diversity, level 3 is not helpful, as different architectures (centralized, decentralized, different network types, etc.) and a focus on different use cases would lead to disproportionate and, therefore, impractical overheads.

The DM3 protocol focuses exclusively on the core protocol's message transmission (level 1). Replication of historical conversations (level 2) is provided as a protocol extension.

## **Gateways to other networks and services**

The DM3 Message Relay Network enables the decentralized transmission of messages between individual users. In addition, a message relay node can serve as a gateway to another network or service. A messaging gateway consists of one or more message relay nodes through which the recipient can be addressed in the DM3 network. Instead of being stored in the cache of the message relay node and kept ready for later retrieval, they are injected into the connected network or service and processed there.

Any existing messaging service or messaging network can be made DM3 interoperable by implementing the following:

1. Publishing user DM3 profiles in ENS names or subnames. This is done, for instance, by connecting the data source via a CCIP resolver. Profiles can also be published directly in ENS if no registry data source exists.
2. Implementing and operating a gateway consisting of a message relay node and a node or client of the connected system.
3. Integration of the DM3 encoder and decoder into the client to read the embedded DM3 message or to encode and wrap a sent message in a DM3 envelope.

Gateways can be operated decentrally and non-custodial. In particular, this means that gateways can (and should) be designed so that no intermediaries can access the content or censor the conversations at any time. All keys are under the exclusive control of the user (or client).

### **Receive messages from the DM3 network**

Messages sent via a gateway are end-to-end encrypted by DM3. They are embedded in a message from the connected system at the gateway and re-encrypted if necessary. To display the message, the receiving client uses a DM3 decoder to decrypt it and to make it readable for the user. This means that messages sent through a gateway are always securely end-to-end encrypted, and the connected system's security, encryption, and privacy are not compromised in any way.

???\[image sent from DM3 to service]

An application (the client) that is made DM3 interoperable in this way must be extended to use the DM3 decoder to extract and decode the embedded DM3 message so that it is readable by the user. These functions are provided by the DM3 SDK.

### **Send messages to the DM3 network**

Messages can also be sent to all other DM3-compatible recipients via the gateways. To do this, the message is first encrypted by a DM3 encoder for the recipient and then packaged as a data packet in a message of the underlying system addressed to the gateway. The gateway extracts the message, which is still DM3 encrypted, and sends it to the recipient using the DM3 message transport protocol.

???\[image sent from service to DM3]

An application made DM3 interoperable in this way must be extended to use the DM3 encoder to first wrap the message in a DM3 envelope (including DM3's end-to-end encryption). The additional encryption of the transport message (in which the DM3 envelope is embedded or sent as an attachment) is added without affecting the end-to-end encryption.\
Furthermore, the application must be extended to address a message to a DM3 profile. These functions are provided by the DM3 SDK.

## **Messaging Bridges**

While gateways are well suited and the best way to integrate networks and services into the DM3 ecosystem, various customizations in the clients are necessary to establish DM3 interoperability.&#x20;

**But what if a messenger, messaging service, or network does not want (or can) cooperate?**&#x20;

Then, messaging bridges are the solution! Messaging bridges aim to enable messages to be sent to other systems without relying on their cooperation or requiring extensions in the receiving system. Changes to their clients, their protocol, or infrastructure are not necessary. All that is needed is an API to inject messages into the system (or receive messages).&#x20;

A messaging bridge is also a message relay node on DM3's side, which can receive messages via the DM3 message transport protocol from any DM3-compatible client. In addition, the Messaging Bridge provides the necessary DM3 profiles for the recipients, thus keeping the DM3 keys in custody. The clients still manage the keys for encryption in the connected service or protocol, ensuring only secure end-to-end encryption according to the connected system.

### **Receive messages from the DM3 network**

To send a message from a DM3 interoperable client, the message is first encoded according to the rules of the receiving system (which usually includes appropriate encryption). If necessary, associated encoders (decoders) are available in the DM3 SDK and APIs.&#x20;

This message is then sent to the bridge (node) as an attachment to a DM3 message. Since the bridge controls the DM3 keys, it can read the (DM3) message. The actual message, encrypted in the attachment, is then forwarded to the connected system via its API. Since the bridge only processes the message encrypted and encoded according to the rules of the receiving system, the content is still securely encrypted end-to-end. The only limitation is that a bridge could censor messages so they are not forwarded to certain recipients.

No changes or extensions are needed in the receiving system.

### **Send messages to the DM3 network**

To send messages from a service to the DM3 network, the Messaging Bridge creates a virtual user to whom the message is sent. However, the message received by the messaging bridge is not decrypted by the bridge but, in turn, embedded in a DM3 message and sent to the recipient. Received in a DM3 interoperable client, it is then decoded accordingly using the DM's SDK containing the connectors (including de- and encoders).

No changes or extensions are needed at the client side of the connected system, as the messages are sent to a virtual user. It would be advantageous if these clients could interact with the DM3 registry for convenience.

### Advantages of Messaging Bridges

Messaging bridges enable establishing a connected messaging ecosystem by using the existing APIs. Even large services that focus on monopolizing the messaging market can be integrated permissionless as long as the corresponding APIs are available (which is enforced in Europe by the Digital Market Act).

Messengers that are DM3-compatible (and use the DM3 SDK), therefore, have access to all connected messaging services without any additional effort. Another advantage is that DM3-compatible messengers do not have to implement and maintain different APIs (as each messenger provides its own interfaces).&#x20;

Being interoperable with DM3 means that all bridges are available and usable. Interoperability via messaging bridges does not compromise a messaging solution's security or privacy. It does not introduce any dependencies or discriminations against other providers, which is often used as an obstacle to interoperability. Each system retains its particular strengths and can also interact with other services. Small and new projects building a DM3 are automatically connected to the other ecosystem players, enabling much better functionality competition instead of keeping and securing existing closed ecosystems.&#x20;

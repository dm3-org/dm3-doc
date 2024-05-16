# Interoperability

Most messengers currently in use are closed ecosystems. Communication between users of different platforms is not possible because the protocols and infrastructures are not compatible or, in the past, even interoperability was actively prevented by the service providers. From the point of view of many users, interoperability is important and desirable. Interoperability can be divided into different levels:

* **Level 1:** New messages can be transferred from one system to another. The storage of messages remains the responsibility of the system
* **Level 2:** In addition to transferring new messages, it is also possible to synchronize saved conversations.
* **Level 3:** All resources can be shared (new messages, historical conversations, configurations, etc.)

Level 1 is required for an interoperable ecosystem; level 2 is useful but not essential. To support the greatest possible diversity, level 3 is not helpful, as different architectures (centralized, decentralized, different network types, etc.) and a focus on different use cases would lead to disproportionate and, therefore, impractical overheads.

The dm3 protocol focuses exclusively on message transmission (level 1) in the core protocol. Replication of historical conversations (level 2) is provided as a protocol extension.

## **Gateways to other networks and services**

The DM3 message relay network enables the decentralized transmission of messages between individual users. In addition, the message relay nodes can also serve as gateways to other networks and services. A messaging gateway consists of one or more message relay nodes via which the recipient can be addressed in the DM3 network. However, they are transferred to the connected system instead of stored in the received messages and kept ready for retrieval.

Any existing messaging service or messaging network can be made DM3 interoperable by implementing the following:

1. Publishing user dm3 profiles in ENS names or subnames. This is done by connecting the data source via a CCIP resolver.
2. Implementing and operating a gateway consisting of a message relay node and a node or client of the connected system.
3. Integration of the dm3 encoder and decoder into the client to read the embedded dm3 message or to wrap a sent message in a dm3 envelope.

Gateways can be operated decentrally and non-custodially. This means, in particular, that gateways can (and should) be designed so that no middlemen have access to the content at any time or could censor the conversations. All keys are exclusively controlled by the user (or the client).

### **Receive messages from the DM3 network**

Messages sent via a gateway are end-to-end encrypted by DM3. At the gateway, they are embedded in a message from the connected system and re-encrypted if necessary. To show the message, the receiving client uses a DM3 decoder to make it readable for the user. This means that messages sent via a gateway are securely encrypted end-to-end at all times, and the connected system's security, encryption, and privacy are not restricted or reduced in any way.

???\[image sent from DM3 to service]

### **Send messages to the DM3 network**

Messages can also be sent to all other DM3-compatible recipients via the gateways. To do this, the message is first encrypted by a DM3 encoder for the recipient and then packaged as a data packet in a message addressed to the gateway. The gateway extracts the message, which is still DM3 encrypted, and sends it to the recipient using the DM3 message transport protocol.

???\[image sent from service to DM3]

## **Messaging Bridges**

While gateways are well suited and the best way to integrate networks and services into the DM3 ecosystem, it is necessary that the various customizations in the clients are necessary to establish DM3 interoperability. But what if a messenger, messaging service, or network does not want to cooperate? Then there are messaging bridges! The aim of messaging bridges is to enable messages to be sent to other systems without having to rely on their cooperation. Changes to their clients, their protocol, or infrastructure are not necessary. All that is needed is an API that can be used to inject messages into the system (or to receive messages). A messaging bridge is also a message relay node on the dm3 side, which can receive messages via the dm3 message transport protocol. In addition, the messaging bridge provides the necessary DM3 profiles for the recipients, which means the DM3 keys are kept in custody.

### **Receive messages from the DM3 network**

To send a message from a dm3 interoperable client, the message is first encoded according to the rules of the receiving system (which usually includes appropriate encryption). If necessary, correspondence encoders (and decoders) are available in the DM3 library and API. This message is then sent to the bridge as an attachment to a dm3 message. Since the bridge controls the dm3 keys, it can read the (dm3) message. The actual message, which is encrypted in the attachment, is then forwarded to the connected system via its API. Since the bridge only processes the message encrypted according to the rules of the receiving system, the content is still securely encrypted end-to-end. The only limitation is that a bridge could possibly censor messages so that they are not forwarded to certain recipients.

### **Send messages to the DM3 network**

To send messages from a service to the DM3 network, the Messaging Bridge creates a virtual user to whom the message is then sent. However, the message received by the messaging bridge is not decrypted by the bridge but, in turn, embedded in a DM3 message and sent to the recipient. Received in a dm3 sub-operable client, it is then decoded accordingly.

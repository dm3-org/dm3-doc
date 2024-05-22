# Protocol extensions

The following protocol extensions are only outlined to show the modular expandability of the DM3 protocol and its applications.

## **Group chat**

Peer-to-peer messaging is defined in the dm3 core protocol. However, many applications also require a group chat function. Group messaging must fulfill the same security and privacy criteria as peer-to-peer messaging.

Two different types are implemented:&#x20;

1. Small groups, based on the peer-to-peer protocol and&#x20;
2. Large groups, based on shared group chat keys.

## **Billboard chat**

The Billboard chat extension provides a public chat that DM3 users can join to participate in the public conversation. The chat history is public, and every added statement has been published. Billboard chats can be used, e.g., as a conference chat or to create public discussion groups.

## **Public Messages**

Public messages are public statements that a user publishes. They can be clearly associated with the user (tamper-proof) but are publicly readable. These public messages can be integrated as social media posts or as status information.

## **Privacy Routing**

Even if the content of DM3 messages is end-to-end encrypted and therefore private, and even if the decentralized message relay node network does not make general tracking of communications possible, monitoring individual nodes would possibly reveal transmission paths. For communications with increased privacy requirements, it is possible to handle the communication between clients and message relay nodes via a privacy network. The dm3 message relay node network itself can also be used to keep the transmission information secret. For this purpose, the message is not sent directly from the client to the receiving message relay node but is first redirected via several (at least 3) nodes. As these nodes only know from whom they receive the packaged message and to whom they should forward it, the connection between the original sender and the recipient is broken after 3 independent forwardings.

Message relay nodes can offer this privacy service as an option. These services can be remunerated via a decoupled incentive system without restricting privacy.

### **Linked Profiles**

Messaging is used in a wide variety of applications. In addition to the main messenger, which represents a user's inbox and is their central communication platform, messaging components can be integrated into other applications (e.g., wallet-to-wallet or app-to-app messaging, support messenger, ...). Usually, these embedded messaging functions are independent and often neither decentralized nor well-secured.&#x20;

With DM3 embedded components and linked profiles (limited-scope profiles), local or application-related profiles can be created and controlled with the same wallet or identity. If required, these can be linked to the user's main inbox so that they can track these communications there.

This allows users to create and maintain anonymous sub-profiles for these applications and link them to the main profile, allowing them to manage important communications in one place.

### **Token gated access**

For various applications, it makes sense that only a limited user group can participate in communication. In centralized applications, access restriction is implemented by central user management. In a decentralized application, access control can be controlled via the possession of tokens or NFTs. With this extension, building closed communities that are fully interoperable with other messengers is also possible.

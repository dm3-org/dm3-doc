---
description: Protocol extensions are modules extending the message transport protocol.
---

# Protocol extensions

Protocol extensions add additional functions and features to the core protocol (DM3 Message Transport Protocol) modularly without breaking the core protocol's leanness. Protocol extensions are not required for implementing DM3 interoperability but offer solutions for many other messaging areas.

The following protocol extensions are only outlined to show the modular expandability of the DM3 protocol and its applications.

## **Group chat**

Peer-to-peer messaging is defined in the Dm3 core protocol ([Message Transport Protocol](../)). However, many applications also require a group chat function. Group messaging must fulfill the same security and privacy criteria as peer-to-peer messaging.

Two different types are introduced:&#x20;

1. Small groups, based on the peer-to-peer protocol and&#x20;
2. Large groups, based on shared group chat keys.

### Small Group Chat

The Small Group Chat is suitable for small chat rooms with up to approx. 15 participants. The protocol extension is based on the peer-to-peer messaging protocol defined in the core protocol. Messages are encrypted separately and sent directly to all participants as direct messages. A group chat registry administers the authorizations of the group participants and manages the group chat history.

Functions for recovering messages not received in the chat history allow effective group management, including subsequent addition of members to the group, etc. The overhead to peer-to-peer is minimal. Effective and decentralized group chat can be implemented as long as the group does not consist of too many participants.

In addition to the members of the group, a list with hashes of all messages belonging to this conversation is also maintained in the group chat registry so that each client can check whether it has received all the messages of the group. If necessary, it can request missing messages from any member of the group, which are then transmitted if the requester is a valid member of the group.

### Large Group Chat

If larger chat rooms are required, the extension for small groups becomes too ineffective, as the messages are sent individually to all participants via the peer-to-peer protocol.&#x20;

For large chat rooms, the peer-to-peer protocol is used to initiate group chats. The participants exchange keys of a virtual user who represents the group chat and the group chat registry is created. Communication is then conducted with the virtual group chat user. All members of the group chat are allowed to fetch the conversations. The group chat then consists of all conversations with the virtual group chat user.&#x20;

Access to the conversations is managed via the group chat registry. The addition or deletion of users can also be linked to a key rotation to ensure that future conversations cannot be fraudulently read.

## **Billboard chat**

The Billboard chat extension provides a public chat that DM3 users can join to participate in the public conversation. The chat history is public, and every added statement has been published. Billboard chats can be used, e.g., as a conference chat or to create public discussion groups.

Similar to a group chat, the chat room consists of all conversations that are held with the virtual user who represents the chat. Encryption is not important here, as the chat history is publicly visible. However, the signatures are significant as they can be used to ensure who the originator of the message (statement) is.&#x20;

Only those who want to actively participate in the conversation need to authenticate themselves; anyone can read along.

## **Public Messages**

Public messages are public statements that a user publishes. They can be associated with the user (tamper-proof) but are publicly readable. These public messages can be integrated as social media posts or status information.

These public statements are solely under the control of the user and are published via IPFS.

## **Privacy Routing**

Even if the content of DM3 messages is end-to-end encrypted and therefore private, and even if the decentralized message relay node network does not make general tracking of communications possible, monitoring individual nodes would possibly reveal transmission paths.&#x20;

For communications with increased privacy requirements, it is possible to handle the communication between clients and message relay nodes via a privacy network (or mix network).&#x20;

The DM3 message relay node network itself can also be used to keep the transmission information secret. For this purpose, the message is not sent directly from the client to the receiving message relay node but is first redirected via several (at least 3) nodes. As these nodes only know from whom they receive the packaged message and to whom they should forward it, the connection between the original sender and the recipient is broken after 3 independent forwardings.

This is done by the sending client first selecting a number of message relay nodes and defining a path for the transmission. The message is then recursively packed into envelopes (onion-skin principle) so that a forwarding node only knows the next recipient (and the sender who delivered the message to it).

Message relay nodes can offer this privacy service as an option. These services can be remunerated via a decoupled incentive system without restricting privacy.

### **Linked Profiles**

Messaging is used in a wide variety of applications. In addition to the main messenger, which represents a user's inbox and is their central communication platform, messaging components can be integrated into other applications (e.g., wallet-to-wallet or app-to-app messaging, support messenger, ...).&#x20;

Usually, these embedded messaging functions are independent and often neither decentralized nor well-secured. With DM3 embedded components and linked profiles (limited-scope profiles), local or application-related profiles can be created and controlled with the same wallet or identity.&#x20;

If required, these can be linked to the user's main inbox so that they can track these communications there. Connected profiles can then mirror the messages in the user's inbox so that important conversations can be integrated and maintained easily and without restriction.

This allows users to create and maintain anonymous sub-profiles for these applications and link them to the main profile, allowing them to manage important communications in one place.

### **Token gated access**

For various applications, it makes sense that only a limited user group can participate in communication. In centralized applications, access restriction is implemented by central user management. In a decentralized application, access control can be controlled via the possession of tokens or NFTs.

With this extension, building closed communities that are fully interoperable with other messengers is also possible.

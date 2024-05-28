# Utility extensions

Additional utility modules provide functions that help build messaging applications but are not directly connected to the messaging core protocol.

## **Embedded Services**

A particular strength of Web3 is its ability to digitize not only information but also interactions with Smart Contracts, interact with values, and make them transferable. With the embedded services extension, additional applications can be integrated into conversations to add interactive applets.

This can be the transfer of tokens in a message or any interaction with other dApps, polls, votes, etc.&#x20;

Frameworks like Farcaster Frames [\[8\]](https://docs.farcaster.xyz/reference/frames/spec) can be integrated.

## **Storage**

The DM3 storage extension provides an effective hierarchical storage scheme for fully encrypted conversations. The focus is on storing conversations and messages to be accessed quickly and efficiently, regardless of whether the data is stored locally, in a database, or in decentralized storage.

Client implementations can use the storage extension to build a hierarchical storage system or connect it to an existing storage scheme.

## **Notification**

Notifying that a message has been received and is waiting to be picked up is crucial to implementing a user-friendly messenger. The notification extension provides various options for such notifications.&#x20;

Particular attention is paid to ensuring that security and privacy are not unintentionally restricted.

Various methods are available for notifying recipients of received messages: email, SMS, browser and app push notifications, Web3-based notifications, etc.&#x20;

In the event that a message is to be sent to an address or name that has not yet published a DM3 profile, notifications can be sent to the potential recipient via NFT-drop so that they can be made aware of this and invited to publish their DM3 profile in order to receive the message.

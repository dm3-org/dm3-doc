---
description: DM3 - secure, decentralized, and interoperable web3 messaging
---

# Introduction

<figure><img src=".gitbook/assets/dm3_banner (1).jpg" alt=""><figcaption></figcaption></figure>

_Digital communication has become an integral part of our lives. Besides e-mail, chat and instant messaging applications are among the most widely used applications on the Internet. While e-mail is utilizing a decentralized architecture but is still largely used unencrypted today, messenger services have become established that often allow end-to-end encrypted communication but are usually operated as centralized services by well-known and powerful tech companies. The services are operated as closed systems; there is no interoperability beyond their borders, and even under current regulations, they are not very suitable for giving users real freedom in their choice of application without having to accept restrictions on communication._&#x20;

_Even if the content of end-to-end encrypted communication appears trustworthy (which cannot be definitively guaranteed in closed systems with proprietary code bases, as backdoors cannot be ruled out), the connection metadata in a centralized system is not private. In addition, censorship cannot be ruled out or even prevented in such services._

_Another problem with current communication services is spam. Depending on the system, this is a profound problem (e.g., in email communication, it can be assumed that at least 50-80% of the messages sent are spam). Filters and extensive, constantly updated blacklists are used in an attempt to curb this problem, which on the one hand, represents an enormous effort and, in many cases, only works inadequately._

_In recent years, many interesting new messaging solutions have emerged that use Web3 technology to realize new approaches to solving these existing problems. While secure end-to-end encryption is state-of-the-art, these Web3 approaches offer good solutions for decentralized and censorship-resistant communication and often excellent privacy._

_However, a problem of the Web2 world threatens to repeat itself here, too: most of these systems are closed ecosystems that cannot interoperate with each other. Although many decentralized protocols are technically excellent for encryption and privacy for special applications, limited scalability makes it impossible for such protocols to serve as an interoperability layer._

_The spam problem has also been insufficiently addressed in Web3 messaging solutions but is essential for building the next-generation messaging ecosystem._



***

## Rethinking Digital Communication

In today's digital age, communication has evolved into an essential facet of modern life, enabling instant connections across the globe. However, the existing communication landscape presents several challenges the DM3 protocol aims to address.

### **The Limitations of Traditional Communication Methods**

**Email's Decentralization and Unencrypted Communication**—Email, an early Internet innovation, initially offered decentralized communication. Yet, it struggled with inadequate spam protection and widespread unencrypted transmission. While protocols emerged to address these concerns, mainstream adoption of encryption remained limited, leaving a significant portion of email communication vulnerable even today.&#x20;

Besides the weak point of missing encryption (which even PGP could not solve due to lack of application), spam became increasingly a significant problem. Today, spam accounts for the largest share of email traffic (60-90%, according to [www.verbraucherzentrale.de](https://www.verbraucherzentrale.de)). This has led to spam filters on the server's side (at the service provider) and on the client's side to filter out a large part of the spam or prevent it from being transmitted in the first place. Another consequence of this is that large email providers today only accept emails from a few other large providers, which results in a situation where it is now almost impossible to host an email service yourself, as the emails sent in this way are not accepted by the spam filters of the large providers.

**SMS and its Encryption Gap**—Short Message Service (SMS) revolutionized communication with its device-to-device text messages. However, SMS messages are transmitted without end-to-end encryption, posing security risks. This encryption gap raises concerns about data privacy in an interconnected world.

With the emergence and eventual triumph of instant messaging applications, which were much less restrictive in terms of how much data and media could be transmitted in addition to text messages and, last but not least, were cheaper, the importance of SMS declined rapidly. Their importance as a means of communication between people beyond the function of service messages has almost disappeared today. Therefore, the interest in introducing innovative improvements has also almost vanished.

**Web2 Messengers and Closed Silos**—In the late 1990s, instant messaging services emerged that made it possible to send direct messages from computer to computer. With the breakthrough of the iPhone and other smartphones at the end of the 2000s and messengers such as WhatsApp, WeChat, Facebook Messenger, Signal, Telegram, and many others, these largely replaced SMS, not least because it was possible to send short messages free of charge.

Even though today, most messengers promise end-to-end encryption for message transmission, in some cases, the encryption may be lifted, e.g., when messages are to be checked for offensive content based on a report of suspicion. Also, as most of these messengers are closed sources, verifying the promise is impossible, and users are expected to trust the providers.

Although most messengers today have a very similar feature set, cross-platform communication is not possible because each messenger maintains its community and keeps data in its silos. Interoperability is currently not possible, and at least in some cases, not even wanted by the providers, although this would be desirable from the user's point of view.&#x20;

Legislative initiatives such as the planned "Digital Markets Act" of the EU ([see](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=celex%3A32022R2065)) and various national drafts aim to make future interactions between users of the different platforms possible. The challenge, however, is that the various solutions have each developed their protocols (with a different focus on security and privacy, for example) and stored user data in their data centers. The opening up of the gatekeepers' systems that the regulators are striving for will not solve the interoperability problem; there is even a serious risk that it will exacerbate the pressure for monopolization.

Most of these solutions also have in common that they are centralized services. Communication always takes place using the servers of the respective service, just as the data (e.g., chat histories, but also metadata such as connection data) is managed by the service providers. In some cases, users have to make far-reaching concessions regarding their sovereignty (e.g., sharing of contact information, etc.).

Often, a certain messenger has become a quasi-standard in a certain region or user group (e.g., WhatsApp in Europe, WeChat in China, Facebook Messenger in the U.S., ...). This leads to the fact that one must also be registered with this service to communicate with friends and acquaintances since they often use the most common messenger and rarely select the messenger based on its technical performance but rather on the network effect in their circle of acquaintances.

`[PIC DATA-SILOS]`

User administration is implemented with username and password (sometimes including 2FA), whereby the telephone number is often used as user identification. However, this also means that the service providers control the user profiles. This means censorship cannot be completely ruled out, connection data can be tricked even if the content is encrypted, and users depend on the service provider.

Even if it is not as severe as email communication, spam is also an issue. It is partly contained by the fact that the operators of the platforms also have user management under their control and respond to spam attacks by blocking or sanctioning these users. The more open these networks are (e.g., through interoperability), the more serious the spam problem becomes. If users are no longer exclusively controlled by one company or organization, the only protection against spam is usually to use suitable filters and blacklists to identify and intercept supposed spam.

### **What is needed?**

To build a messaging ecosystem that is&#x20;

* secure,&#x20;
* protects the privacy of communications and&#x20;
* is also interoperable,&#x20;

it is necessary to focus on the following basic features:

**Secure End-to-End Encryption**—Secure end-to-end encryption is state-of-the-art and must be the foundation of all communication protocols, platforms, and services.

**Decentralization**—Centralized systems have the general problem that censorship cannot be prevented and/or that there are single points of failure whose failure or malfunction can lead to the failure of the entire system or at least portions of it. With a decentralized architecture not controlled by a single entity (a company, organization, or government), censorship-resistant, fail-safe systems can be built. Consequently, this is also important for the messaging ecosystem of the future.

**Privacy**—Privacy is not just a nice-to-have but a fundamental right. Even if there are different requirements for the degree of privacy in our communication (an in-app chat function in a game may have fewer requirements than, for example, the communication of a whistleblower to an investigative journalist), modern communication systems must meet the requirement of enabling private communication without adding ideological complexity. Sound messengers and messaging protocols must meet this requirement.

**Interoperability**—For the end user, it does not matter which service or system their communication partner uses as long as the messages can be exchanged. As interoperability and compatibility are completely normal in many application areas, interoperability must also be the standard for messaging. Technical diversity is good in many cases. Solutions tailored to specific ecosystems or applications often offer better UX but can only be used by a larger user group if they can interoperate with others.&#x20;

Although interoperability can be achieved using the same core protocol and possibly the same infrastructure, this is not expedient in the current situation, as different systems with different core systems, requirements, and goals are active and widely accepted.

What is needed is an interoperability protocol that can serve as a core protocol (layer 1) for new solutions but can also connect existing protocols and services (layer 0) without compromising the security, privacy, and UX of existing solutions. Such a protocol must be lean and fundamentally scalable.

**Spam-Protection**—The omnipresent problem of spam must be solved sensibly, as otherwise, interoperability, in particular, will lead to even more strain. It is essential that better methods than the existing filters and blacklists are used. Web3, in particular, provides us with suitable tools to solve the spam problem once and for all.

### **What is essential?**

It is particularly important to focus on the essential functions when setting up a protocol intended to establish interoperability between various existing and new protocols, services, and applications. These are

1. A scalable, decentralized, scalable, trustless, and permissionless network for transmitting messages.
2. A decentralized, trustless, and permissionless registry for the communication profiles (public keys for encryption and signatures, and information on how and where messages have to be delivered).
3. A lean and modular protocol that supports the above features and that can be used both as a layer 1 and as a layer 0 protocol and that does not introduce any restrictions compared to existing systems.

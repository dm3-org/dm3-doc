---
description: >-
  Solving Fragmentation and Privacy Challenges in Web3 Messaging: The dm3
  Protocol
---

# Executive Summary

## TL;DR

**TL;DR:**

The DM3 protocol addresses critical challenges in Web3 messaging, such as fragmentation, lack of interoperability, spam, and privacy concerns. With over 40 Web3 messaging solutions in development, none offer seamless communication across platforms. DM3 introduces a scalable, decentralized messaging network that leverages ENS-based identities, economic incentives for spam protection, and interoperability between existing messaging protocols. The protocol also integrates AI for private messaging assistance and aims to become the core standard for secure, interoperable communication in both Web3 and traditional ecosystems.

## Problem/Motivation:

Enhancing global communication has been one of the Internet's greatest successes, yet significant challenges remain. Modern messaging solutions are plagued by fragmentation, lack of universal standards, vendor lock-in, spam, impersonation, and inadequate privacy protection. These issues are becoming more apparent and pressing as digital communication evolves. We believe that by applying the core principles and decentralized architecture of Web3 to the messaging domain, we can address these challenges and unlock a new era of secure, seamless, and interoperable communications.

### The current landscape of messaging solutions

<table data-header-hidden><thead><tr><th></th><th width="295"></th><th></th></tr></thead><tbody><tr><td><strong>Web1 (Email)</strong></td><td><strong>Web2 (Messengers)</strong></td><td><strong>Web2 (Social Networks)</strong></td></tr><tr><td><p>+ Interoperable</p><p>+ Standardized</p><p>+ Decentralized</p></td><td>+ UX<br>+ Convenient <br>+ Encryption</td><td>+ Easy discovery<br>+ Convenient</td></tr><tr><td><p>- Obsolete</p><p>- No discovery</p><p>- Impersonation</p><p>- Vendor lock-in</p><p>- Spam</p><p>- Lack of privacy</p><p>- Lack of encryption</p><p>...</p></td><td><p>- Fragmentation</p><p>- Closed ecosystems</p><p>- No Interoperability</p><p>- Vendor lock-in</p><p>- Spam</p><p>- Lack of privacy</p><p>- Deplatforming</p><p>...</p></td><td><p>- Fragmentation</p><p>- Vendor lock-in</p><p>- Closed Ecosystems</p><p>- No interoperability</p><p>- Spam</p><p>- Lack of privacy</p><p>- Deplatforming</p><p>- No private messaging</p><p>...</p></td></tr></tbody></table>

Attempts to build Web3 native messaging platforms/protocols have resolved some of these issues, e.g., immutable identities by wallets or privacy (Waku, XMTP, ...), albeit there are still fundamental challenges:

* **Fragmentation/Lack of interoperability**—\
  More> than 42 Web3 messaging solutions are being developed (Waku/Status, XMTP, Wallet Connect, MailChain, Ethermail, Blockscan Chat, WalletChat, …). Most solutions are still closed ecosystems without interoperability with other solutions.\
  Many of those have raised significant funds (status: $105M\*, xmtp: $25M, Ethermail: $7M, MailChain $4.6M,  WalletConnect $25M\*,... source: [https://icodrops.com](https://icodrops.com), \* messaging is only part of the business).
*   **Low start problem**—

    A small group of users, still no network effect, and no one has yet created enough new functionality to encourage users to migrate their communications to new channels).\
    Compared with well-known web2 messengers, user communities are tiny (currently <1%).
* **Low scalability**—\
  Web3-based messaging solutions often build on broadcast networks (whisper, waku, xmtp, ...); while fitting well to particular use cases, such solutions are not scalable by design but need notable innovation yet to be developed to become able to handle many messages.
* **Spam**— \
  There is still a problem (e.g., chat in Coinbase Wallet based on XMTP).
* **No universal use**—\
  Because of missing interoperability, having a direct, secure conversation with wallets is still impossible.&#x20;
* **Lack of decentralization**—\
  Many solutions are still operated centralized, with the risk of single points of failure and potential privacy lacks.

**DM3** attempts to solve all these problems by:

1. **Creating a public registry for communication profiles** based on ENS and integrating any L2, other L1s, and cloud-based solutions that enable secure and private communication.
2. **Building a decentralized network of Message relay nodes** that is scalable by design and enables self-sovereign communication.
3. **Introducing** a lean, open, and easy-to-integrate **interoperability solution** for Web1/2/3 messaging protocols and solutions, including a comprehensive SDK.
4. Leveraging economic incentives to introduce Web3 native **spam protection.**
5. Providing **AI-based** but privacy-preserving **messaging assistance**. &#x20;

We are not creating yet another messenger but rather a core protocol (think of the Internet's core protocol, TCP/IP) that allows existing messaging protocols to interoperate efficiently and new messaging solutions to be built directly on top of it. Also, dm3 enables solutions like wallets, Web3 games, marketplaces, etc., to easily integrate secure and interoperable messaging.

## But why now?

### Web2 momentum:

* Centralized messengers are increasingly the focus of regulation (e.g., Durov's (Telegram) arrest narrative, the "Digital Markets Act," and proposed chat control of the EU, etc.).
* Prominent messengers control the market and prevent new and innovative solutions.
* Closed and centralized systems often provide only limited privacy and security and avoid real interoperability. Impersonation, spam, and scam/phishing attacks are increasing.
* Chatbots play an increasingly important role in many systems, undermining trustworthy communication.

### Web 3 momentum:

* **Wallets as Identities**—\
  As wallets and user-friendly name representations (using name services like ENS) evolve into unique digital identities, the need to facilitate not only transactions but also direct communication with specific wallets becomes crucial. The shift towards wallets being more than just financial tools underscores the importance of integrated messaging capabilities.
* **Proliferation of Messaging Protocols**—\
  With over 42 messaging solutions in development, the Web3 ecosystem is facing a significant fragmentation challenge. While other layers of the Web3 stack (like blockchains, DeFi, NFTs, and social platforms) have started to adopt aggregation and interoperability solutions, messaging remains highly fragmented. Unlike DeFi, where fragmentation impacts liquidity and pricing, fragmentation in messaging creates a more severe issue—complete communication breakdowns across platforms.
* **The emergence of Web3 Social Platforms**—\
  Web3 social platforms like Farcaster are gaining traction, but interoperability challenges persist. For example, there’s currently no seamless way to send messages from Warpcast to Lens, highlighting the urgent need for interoperable messaging solutions.
* **Convergence of Wallets and Messengers**—\
  Integrating wallets with messaging apps (e.g., Telegram + TON Wallet, Coinbase Wallet + XMTP) is becoming more common. Technologies like Telegram Mini Apps and Farcaster Frames are turning the wallet-messenger combo into the primary gateway for new users entering the Web3 world. However, this trend also risks breaking the composability that is central to Web3, further emphasizing the need for a unified, interoperable messaging protocol.

## Solution

With DM3, we provide a lean messaging protocol to connect existing solutions, enable new solutions, and establish a connected messaging ecosystem while consistently implementing Web3 ideals like decentralization, secure encryption, censorship resistance, privacy, etc.\
For detailed information, see [here](./#unique-features).&#x20;

## How the future of messaging looks like:

* Directly reach a specific person by his/her ENS/wallet/social network handle/name. They will receive a message in the app that it is convenient for them. Attract their attention by staking tokens.
* Single inbox: Get all your emails/messages in a single application. Use the client you prefer, whether a simple mobile application or a complex CRM system. Connect any local messaging (like in-app messaging of a particular app) to your inbox and control all your relevant conversations in one place.
* You can use all the functionality of Web3 inside messages via frames: send money, place bets, vote, etc.
* Set the level of message encryption and privacy as you need.
* Be 100% sure who sent you the message. No impersonated senders can trick you into scams.
* Let spammers pay and lose money if they send spam to your inbox. Increasing the sender's anti-spam deposit requirement keeps your inbox free of spam.
* You can use AI assistance within your messenger without the risk of losing privacy or sharing confidential information outside your inbox.

## Use Cases

The use cases describe various possible applications of DM3 technology and the DM3 network. The listed examples are applications that have already been analyzed and discussed or are already in the planning or implementation stages.

* **Embedded Messaging use-case:**\
  By simply connecting your wallet, you can send a message to an organization on its website or from user to user in a dApp. You can get a response wherever it is convenient for you. You can also link this conversation to your inbox. These chats can be direct conversations with persons, support chats, or similar. This can be an embedded messaging component or a simple button opening a messenger popup.\
  _Examples:_&#x20;
  * _polymorphic.capital_ website with direct messages to partners
  * Embedded messenger in _rethinkable.xyz_ (social media app)
* **Core-Protocol use-case:**\
  An innovative new messenger solution uses the DM3 protocol as its core. Users of this messenger are connected with any other DM3-interoperable messenger and can send messages to users of other messengers while using a new messenger.\
  _Examples:_
  * The _Hicoiny_ messenger utilizes DM3 as the core protocol
* **Interoperability use-case**\
  An existing messenger adds DM3 interoperability to join the DM3 messaging network. Users of this messenger can send and receive messages to and from any other messenger. Messaging bridges enable message exchange for other messengers. \
  _Examples:_
  * _Wallet Connect_ web3 inbox can send and receive DM3 messages.
  * _XMTP_ inbox can send and receive DM3 messages.
  * Any DM3 interoperable messenger can send messages to any _Telegram_ user.
  * Any DM3 interoperable messenger can send messages to any _WhatsApp_ user.
* **Ecosystem use-case:**\
  Send messages to other profiles seamlessly within your profile or any dApp in that ecosystem. With DM3 as the messaging standard in this ecosystem, users of dApps in this exosystem can communicate.\
  _Examples:_
  * _Lukso/universal profiles_ use DM3 as the native messaging protocol
  * _Gnosis name service GENOME_ is natively supported by DM3
  * _BNB_ uses DM3 as a native messaging protocol for web3 games of this ecosystem
  * _ENS_ provides direct messaging support for ENS names that publish communication profile
  * _SpaceID_ provides direct messaging support for ENS names that publish communication profile
* **Wallet-to-Wallet use-case:**\
  Send messages to other signers in the multisig-wallet to coordinate multi-signature transactions without using another application. \
  _Examples:_
  * _Gnosis Safe_ embedded messenger is fully integrated into the signing process.
* **Web3-game use-case:**\
  Create a messaging group within the game to synchronize with other players.
* **Marketplace use-case:**\
  Send a confidential message directly to the provider of an NFT in the marketplace.
* **SDK use-case:**\
  Messaging solutions or any other applications are built using the DM3 SDK.&#x20;

## Go-to-market

* **Stage 1:** Gain initial traction in Web3
  * Become a standard messaging protocol for major ecosystems (Optimism, Gnosis, Lukso, etc.)
  * Become a standard for embedded messaging for dApps.
  * Enable existing web3 messaging solutions to become DM3 interoperable.
* **Stage 2:** Become a major messaging solution for Web3 native users
  * As many dApps and web3 ecosystems use DM3 as a native messaging core protocol, web3 users use any DM3 messenger to communicate
  * Every Web3 name (Web3 name services like ENS and those in L2s and other chains) has a communication profile and can converse with other users, regardless of their messenger.&#x20;
  * Existing Web3 messaging protocols become DM3 interoperable and join the connected messaging ecosystem.
  * New Web3 messaging solutions are built on top of DM3 as the core protocol, making them interoperable in the connected messaging ecosystem from day one.
  * The DM3 SDK is used for messaging solutions
* **Stage 3**: Beyond Web3 natives
  * Any commonly used messenger is connected to the DM3 messaging network with a messaging bridge or gateway. Web3 users can send messages to users of any messenger.&#x20;
  * Existing web3 messaging protocols become DM3 interoperable and join the connected messaging ecosystem.
  * The DM3 core protocol becomes an interoperability standard for messaging.
* **Stage 4:** Extended Function
  * AI Messaging Assistant becomes adaption to increase UX and address regulatory requirements for messaging while preserving privacy&#x20;

## Business/Operation Model

The organization dm3.org gGmbH is a German non-profit limited liability company (“gemeinnützige GmbH”) coordinating specifications, development, and external contributions. All software and specification documents are published as open-source and public goods.

The value is in the DM3 network (represented by the DM3 token).

The DM3 Token is the utility token of the DM3 network with the following functions:

* Network utilities (spam protection, network services like enhanced privacy)
* Governance
* Standardization incentive

### Token economics

The DM3 token economic model centers on using DM3 tokens for network utilities, governance, and incentives for standardization. For instance, to reduce spam, users must deposit DM3 tokens as a promise not to send spam. If spam is detected, these tokens are burned, effectively deterring malicious activity.

Additionally, DM3 tokens are utilized to purchase network services such as enhanced privacy and delivery options, further driving demand as the network expands.&#x20;

As users increase, so does the demand for anti-spam deposits and network services, ensuring the tokens' continued demand. Regarding governance, DM3 token holders or their delegates participate in protocol decisions, voting on upgrades, and resource allocation. This decentralized governance ensures that users influence the protocol's evolution.

Tokens are also distributed to the community and partners to incentivize and drive standardization.

## Traction

The DM3 core protocol and DM3 embedded components are specified and implemented, and a reference implementation and the first network infrastructure are published and operational.

In the specification process, we talked to and aligned with many existing Web3 messaging solutions to evaluate the requirements for a standard interoperability protocol. The results of these consultations have been incorporated into the protocol specification's architecture and modules.\
**The specification of the DM3 core protocol (Message Transport Protocol) and the DM3 core architecture align with the requirements needed to build the interoperability layer.**

In particular, it has also been realized that, besides the Ethereum ecosystem, any other L1s or L2s and cloud services can be connected to the standardized communication registry. This allows the DM3 protocol to be integrated as a native messaging protocol in different ecosystems. \
**To enable DM3 to support different ecosystems, we specified and developed the cross-chain communication registry with links to cloud services, L2s, and L1s.**

We also aligned requirements with many dApps (wallets, marketplaces, Web3 games, Web3 social media, etc.) for embedded messaging.\
DM3 embedded components were developed and added to the first applications as part of the SDK development. In addition to these embedded use cases, applications started to be built entirely on top of DM3.&#x20;

### Integrations:

* **The DM3 reference implementation**\
  The reference implementation is based on the embedded components. It is available as a reference instance. This integration is live.
* **Lukso/Universal Profiles**—\
  We are currently completing the integration into the Lukso Ecosystem so that DM3 can be directly integrated into Universal Profiles and used as the standard messenger and messaging protocol in this ecosystem. Various dApps can also incorporate it.
* **CommonGround**—\
  With CommonGround, we started integrating an existing messaging and web3 community solution into the DM3 network by implementing DM3 as the interoperability layer for direct messages. The integration is in progress.
* **Hicoiny Messenger**—\
  Hicoiny, a new messenger focused on a token-sharing community, is in the process of developing DM3 as the core protocol for this solution.
* **MASQ Network**—\
  The MASQ network is a privacy network utilizing a mesh VPN. DM3 is supported as an internal messenger.
* **Rethinkable.xyz**—\
  Rethinkable, the LinkedIn-like social network for Web3, will use DM3 as an internal messenger to enable users to communicate directly. This integration is in the planning phase.
* **ENS (Ethereum Name Service)**—\
  DM3's communication profiles are published in ENS (optional records "network.dm3.profile"). Other data sources, such as could services, L2s, and L1s, are linked to ENS subdomains. \
  ENS integrated the direct link to DM3 to send messages directly to the identity owner into their POAP app (linked to commonly used ENS NFC identity cards). This integration is finished.\
  Also, the DM3 embedded messenger is planned to be included in the ENS app, allowing name owners with a communication profile to be contacted directly via DM3. This integration is in planning right now.
* **GENOME (Gnosis Name Service)**—\
  DM3's communication profiles can be published in GENOME (Gnosis, Arbitrum, BNB, ... in records "network.dm3.profile"). The data is linked to ENS to the subdomain gnosis.eth. The DM3 messenger (DM3 embedded) can be used natively in the Gnosis ecosystem.
* **SpaceID (Name service provider for several ecosystems)**—\
  DM3's communication profiles can be published in several SpaceID-provided ecosystems (Gnosis, Arbitrum, BNB, ... in records "network.dm3.profile"). The data is linked to ENS to a subdomain. The DM3 embedded messenger is planned to be included in the SpaceID app, allowing name owners with a communication profile to be contacted directly via DM3. This integration is in the planning or concept phase right now.
* **Optimism**—\
  Optimism is connected to be the Registry Location. Users can store their communication profiles in Optimism. DM3 can be used natively as a messaging protocol on Optimism-based apps. This integration is implemented.
* **Arbitrum**—\
  Arbitrum is connected to be the Registry Location. Users can store their communication profiles in Arbitrum. DM3 can be used natively as a messaging protocol on Arbitrum-based apps. This integration is in progress.
* **Base**—\
  Base is connected to be the Registry Location. Users can store their communication profiles in Base. DM3 can be used natively as a messaging protocol on Base-based apps. This integration is in planning.
* **Streameth (EthPrague, DevConnect)**—\
  DM3 (with the Billboard Chat Extension) is integrated as an official conference live chat for the conference live streaming portal. It was used at EthPrague 2023 and several Events at DevConnect 2023 (Istanbul). This integration was live (while
* &#x20;restricted to the conference).
* **Mithraeum**—\
  Mithraeum is a web3 game. DM3 is planned to be used as an embedded messenger (in-game messenger). This integration is in planning.
* **Gnosis Safe**—\
  DM3 is planned to be integrated as a wallet-to-wallet chat in Gnosis Safe. An MVP implementation is already implemented, and the integration is in the concept phase.
* **Niftyfair**—\
  Niftyfair is an NFT marketplace. DM3 is intended to become the internal marketplace messenger providing direct communication between buyers and sellers. This integration is in planning.
* **Polymorphic.capital Website**—\
  DM3 is used to direct message partners and associates. This integration is in progress.
* **POAP App**—\
  The POAP (Proof-of-Attendance-Protocol) app offers information to the POAP issuer. It is intended to add the direct messaging contact to the issuer so that holders can directly communicate with the issuer. This integration is in concept.

## Why DM3?

With the DM3 protocol, we have specified and built the first Web3 messaging protocol based on Web3 values while also enabling interoperability. The core protocol's extremely lean architecture and modularity allow new apps to build on it and existing solutions to become interoperable without compromising their security, privacy, or UX.&#x20;

Furthermore, because DM3 is scalable by design, it is the first available solution suitable for establishing and successfully expanding the connected messaging ecosystem, whereby existing solutions from the Web2 and Web3 worlds can be integrated.

The systematic and practical use of Web3 technology (e.g., for the communication profile registry, spam protection, ...) and AI (e.g., for private messaging assistants) solves the fundamental problems of existing systems.

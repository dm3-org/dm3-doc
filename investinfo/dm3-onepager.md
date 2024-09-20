# DM3 Onepager

## Problem/Motivation:

Enhancing global communication has been one of the Internet's greatest successes, yet significant challenges remain. Modern messaging solutions are plagued by fragmentation, lack of universal standards, vendor lock-in, spam, impersonation, and inadequate privacy protection. These issues are becoming more apparent and pressing as digital communication evolves. We believe that by applying the core principles and decentralized architecture of Web3 to the messaging domain, we can address these challenges and unlock a new era of secure, seamless, and interoperable communications.

### The current landscape of messaging solutions

| **Web1 (Email)**                                                                                                                                         | **Web2 (Messengers)**                                                                                                                                                    | **Web2 (Social Networks)**                                                                                                                                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>+ Interoperable</p><p>+ Standardized</p><p>+ Decentralized</p>                                                                                        | <p>+ UX<br>+ Convenient <br>+ Encryption</p>                                                                                                                             | <p>+ Easy discovery<br>+ Convenient</p>                                                                                                                                                               |
| <p>- Obsolete</p><p>- No discovery</p><p>- Impersonation</p><p>- Vendor lock-in</p><p>- Spam</p><p>- Lack of privacy</p><p>- No Encryption</p><p>...</p> | <p>- Fragmentation</p><p>- Closed ecosystems</p><p>- No Interoperability</p><p>- Vendor lock-in</p><p>- Spam</p><p>- Lack of privacy</p><p>- Deplatforming</p><p>...</p> | <p>- Fragmentation</p><p>- Vendor lock-in</p><p>- Closed Ecosystems</p><p>- No interoperability</p><p>- Spam</p><p>- Lack of privacy</p><p>- Deplatforming</p><p>- No private messaging</p><p>...</p> |

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

1. **Creating a public registry for communication profiles** based on ENS and integrating any L2, other blockchains, and cloud-based solutions that enable secure and private communication.
2. **Building a decentralized network of Message relay nodes** that is scalable by design and enables self-sovereign communication.
3. **Introducing** a lean, open, and easy-to-integrate **interoperability solution** for Web1/2/3 messaging protocols and solutions
4. Leveraging economic incentives to introduce Web3 native **spam protection.**
5. Providing **AI-based** but privacy-preserving **messaging assistance**. &#x20;

We are not creating yet another messenger but rather a core protocol (think https) that allows existing messaging protocols to interoperate efficiently and new messaging solutions to be built directly on top of it. Also, dm3 enables solutions like wallets, web3 games, marketplaces, etc., to easily integrate secure and interoperable messaging.

## Why now?

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
  The integration of wallets with messaging apps (e.g., Telegram + TON Wallet, Coinbase Wallet + XMTP) is becoming more common. Technologies like Telegram Mini Apps and Farcaster Frames are turning the wallet-messenger combo into the primary gateway for new users entering the Web3 world. However, this trend also risks breaking the composability that is central to Web3, further emphasizing the need for a unified, interoperable messaging protocol.

## Solution

With DM3, we provide a lean messaging protocol to connect existing solutions, enable new solutions, and establish a connected messaging ecosystem while consistently implementing Web3 ideals like decentralization, secure encryption, censorship resistance, privacy, etc.\
For detailed information, see [here](./#unique-features).&#x20;

## How the future of messaging looks like:

* Directly reach a specific person by his/her ENS/wallet/social network handle/name. They will receive a message in the app that it is convenient for them. Attract their attention by staking tokens.
* Single inbox: Get all your emails/messages in a single application. Use the client you prefer, whether it is a simple mobile application or a complex CRM system. Connect any local messaging (like in-app messaging of a particular app) to your inbox and control all your relevant conversations in one place.
* You can use all the functionality of Web3 inside messages via frames: send money, place bets, vote, etc.
* Set the level of message encryption and privacy as you need.
* Be 100% sure who sent you the message. No impersonated senders can trick you into scams.
* Let spammers pay and lose money if they send spam to your inbox. By increasing the sender's anti-spam deposit requirement, you keep your inbox free of spam.
* You can use AI assistance within your messenger without the risk of losing privacy or sharing confidential information outside your own inbox.
* Polymorphic use-case: Send a message to an organization on its website by simply connecting your wallet. Get a response wherever it is convenient for you. Link this conversation to your inbox if you want.
* Lukso use-case: Send messages to other profiles seamlessly within your profile or any dApp in that ecosystem.
* Gnosis-Safe use-case: Send messages to other signers in the multisig-wallet to coordinate multi-signature transactions without the need to use another application.
* Web3-game use-case: Create a messaging group within the game to synchronize with other players.
* Marketplace use-case: Send a confidential message directly to the provider of an NFT in the marketplace.

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
* **Stage 3**: Beyond Web3 natives
  * Any commonly used messenger is connected to the DM3 messaging network with a messaging bridge or gateway. Web3 users can send messages to users of any messenger.&#x20;
  * Existing web3 messaging protocols become DM3 interoperable and join the connected messaging ecosystem.
  * The DM3 core protocol becomes an interoperability standard for messaging.

## Business/Operation Model

The organization dm3.org gGmbH is a German non-profit limited liability company (“gemeinnützige GmbH”) that coordinates specifications, development, and external contributions. All software and specification documents are published as open-source and public goods.

The value is in the DM3 network (represented by the DM3 token).

The DM3 Token is the utility token of the DM3 network with the following functions:

* Network utilities (spam protection, network services like enhanced privacy)
* Governance
* Standardization incentive

### Token economics

The DM3 token economic model centers on using DM3 tokens for network utilities, governance, and incentives for standardization. For instance, to reduce spam, users must deposit DM3 tokens as a promise not to send spam. In the event that spam is detected, these tokens are burned, providing an effective deterrent for malicious activity.

Additionally, DM3 tokens are utilized to purchase network services such as enhanced privacy and delivery options, which will further drive demand as the network continues to expand.&#x20;

As users increase, so does the demand for anti-spam deposits and network services, ensuring the tokens' continued demand. Regarding governance, DM3 token holders or their delegates participate in protocol decisions, voting on upgrades, and resource allocation. This decentralized governance ensures that users influence the protocol's evolution.

Tokens are also distributed to the community and partners to incentivize and drive standardization.

## Traction

The DM3 core protocol and DM3 embedded components are specified and implemented, and a reference implementation and the first infrastructure of the network are published and operational.

In the specification process, we talked to and aligned with many existing Web3 messaging solutions to evaluate the requirements for a common interoperability protocol. The results of these consultations have been incorporated into the protocol specification's architecture and modules.

In particular, it has also been realized that, in addition to the Ethereum ecosystem, any other L1s or L2s and cloud services can be connected to the standardized communication registry. This makes it possible for the DM3 protocol to be integrated as a native messaging protocol in different ecosystems.&#x20;

To this end, we have entered into partnerships with ENS, Optimism, Arbitrum, Gnosis, Lukso, and SpaceID.&#x20;

### Examples:

We are currently completing the integration into the Lukso Ecosystem so that DM3 can be used as the standard messenger in this ecosystem, and various dApps can also integrate it.

With CommonGround we started to integrate an exsting messaging solution

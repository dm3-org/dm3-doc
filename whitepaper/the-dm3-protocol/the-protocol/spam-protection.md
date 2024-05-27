# Spam Protection

## Spam Protection

Spam is a major challenge in current communication systems. According to a survey , between 50% and well over 90% of all emails sent are classified as spam. However, spam and the fight against it is also important in larger messenger services. Centralized systems generally find it somewhat easier to take action against spam, as they can censor more easily via their central infrastructure than in decentralized infrastructures (such as email). All widely used approaches to curbing spam are based on blocking messages suspected of being spam. With web3-based methods, however, it is possible to go further and make sending spam so unattractive for the sender that the motivation to send spam is no longer there. The DM3 protocol uses a web3-based multi-level spam defense system, which in combination makes spam unprofitable for the sender while not significantly hindering the desired communications.

### **Black- and Whitelists**

**Blacklists** are a common method of filtering messages from proven malicious senders. In terms of web3-based communication, this means that addresses that have become conspicuous are included in such lists and can then be filtered out. This makes it possible to use public lists of known scammers and spammers for pre-filtering. As all messages in DM3 are signed by the sender, it is not possible for spammers to use the identity of others to send messages. This method should be combined, as it cannot provide reliable protection against spam. However, blacklists in web3 are only effective to a limited extent, as a spammer can easily keep generating new addresses that are not yet on the blacklist. Blacklists are mainly used to evaluate public lists (e.g., on which sanctioned users are noted).

**Whitelists** are suitable for giving preferential treatment to addresses that the user trusts. This makes it easy to exclude addresses on such a list from the check of further criteria described in the following paragraphs.

The message relay node can already execute these methods, so potential spam is not even accepted.

### **Proof-of-Activity**

If the sender's address has a nonce greater than 1 (or a number > 1 specified by the recipient), it is regarded as proof of activity. This ensures that this address has already been active and transactions have been executed. This is usually not a problem for a "normal" wallet address of an active wallet.

However, if spammers try to send spam from newly generated addresses, they would first have to carry out transactions before they could use these addresses to send spam. This costs both money (transaction fees) and time (until the transaction is added to the blockchain). It also massively limits the number of possible new addresses. While a spammer could create an unlimited number of new addresses, the number of "used" addresses depends on the blockchain's capacity, as at least one transaction would have to originate from each address.

This method is well suited to preventing spam attacks, in which spammers constantly generate new addresses to circumvent block lists. The message relay node can already execute this method, so potential spam is not even accepted.

### **Proof-of-Ownership**

Another way to make sending spam unattractive is to require the sender to hold a certain number of tokens or an NFT from a certain collection on their wallet. This also prevents newly generated addresses from being used to send spam, as the spammer would then have to equip all these addresses with these tokens.

This is not a relevant challenge for regularly used wallets. To send a message to a recipient who requires this condition, the required tokens must be transferred to the wallet. However, possessing exotic tokens or very high amounts should not be required, as this may represent an obstacle to use.

However, this also results in high costs and expenses for the potential spammer if he first has to equip each new address with tokens before it can be used for sending. This method can already be executed by the message relay node, so potential spam is not even accepted.

### **Token Stake and Burn**

While the methods already listed serve to limit mass spam in particular, a next level of spam protection is being introduced.

Each recipient defines how many DM3 tokens a sender has to deposit as security to guarantee that the message is not spam or scam. For a sender to be able to submit a message to the recipient's message relay, it must have deposited at least the required amount. Only then will the message relay accept the message. If the recipient declares the message as spam, part of the deposit is burned, and the spam sender is penalized. In this way, the spam sender can be penalized at any cost, so sending spam is no longer profitable. If the message is accepted, the deposit will not be affected. This means that nothing happens in regular conversations and the sender does not have to fear any loss. The message relay can also check whether the sender has deposited a sufficiently high deposit. The execution of the punishment for spam requires interaction with the receiving client.

# Chapter Wise Questions

## Week 1, Chapter 1 (Finite Fields) + Chapter 2 (Elliptic Curves)

- What is a modulo operation? What are the mathematical properties of finite fields? Why are these properties important to have?	

- Can you explain in simple terms what does order of a finite field means? Why finite fields are constructed with a prime modulo? What happens if its not a prime?	

- Explain Fermat's little theorem. What is it used for?

- How to express negative numbers in finite field? What would be the positive number equivalent of -27mod(5)?

- What is an elliptic curve? What was the earliest known elliptic curve? Why elliptic curves are useful in cryptography?

- Explain elliptic curve point addition in simple terms.

- For elliptic curve point addition the last step is to reflect the resulting point across x-axis. Why is this needed? What happens if there was no reflection?

- What is the Point of Infinity? What curve operation produces the point of Infinity? Is it useful in real life crypto implementation?

## Week 2 : Chapter 3 (Elliptic Curve Cryptography)

- What are elliptic curves over finite fields, and how do they differ from normal elliptic curves? Are there any changes in properties between an Elliptic Curve over Finite Fields and Real Numbers?

- What is the Discrete Log Problem, and why is it important in Cryptography? What does it mean when we say "DLP is hard"? What would have happened if DLP wasn't a "hard" problem?

- What is a Mathematical Group, and what properties must a group maintain? What happens if the group operation isn't commutative?

- What is secp256k1, and are there other curves similar to it? What makes 256k1 special, and over what finite field is it defined?

- What is the generator point, and how is it determined for a specific curve? Is it chosen randomly? Why did Satoshi choose secp256k1 for Bitcoin?

- What are Private Keys and Public Keys in the context of elliptic curves? Can you briefly explain the process of generating Private and Public Keys?

- What are Public Key additions, and what is the result of adding two public keys? Where can the addition of keys be useful?

- What is a Digital Signature, and what is its purpose? What does a Digital Signature ultimately prove? How many different types of Digital Signature algorithms are known, with ECDSA being one of them?

- Can you provide a brief description of the Signature Creation and Verification algorithms? Which one takes more time? Bonus: Can you give a real example of the average time taken on your machine for a single ECDSA creation and verification?

- Why is it important to have a "unique K"? What vulnerabilities can be exploited if K is known to be reused? Can you provide a real-life example of when such an exploit occurred?

## Week 3: Chapter 4 (Serialization) + Chapter 5 (Transactions)

- What is the Wallet Import Format (WIF) used for, and how is it generated from a private key?

- How is the compressed SEC format serialised for a point P = (x,y)?

- Briefly outline the process of creating a Bitcoin address. Which hash operation is used, and what is the purpose of the checksum?

- How does Base58 encoding addresses some of the potential issues or limitations of Base64 encoding?

- Explain DER signature encoding with an example.

- Why does a transaction require a version, and what does it signify with respect to upgradability?

- How is the transaction fee determined, and why doesn't it have a dedicated field in the transaction structure?

- Explain different types of timelocks which you can have and list the components of the transactions that can be used to set timelocks.

- Why don't inputs specify the amount directly? How is the amount determined for each input?

- Why was the original idea for using the sequence and locktime fields for "high-frequency trades" considered insecure?

## Week 4: Chapter 6 (Script) + Chapter 7 (Transaction creation)

- Highlight the differences between native segwit and nested segwit? Which is better? Why nested segwit was required? Discuss script execution of nested segwit scripts.

- What are the differences between P2SH and P2WSH? Which is better in terms of security and why?

- What are non-standard output scripts? Give an example. Is there a way to use non-standard script on bitcoin network?

- What are OP_NOPs? Why do we have them in bitcoin? Why CLTV and CSV opcodes have to be succeeded with OP_DROP opcode? Will other OP_NOPs also have to be followed by OP_DROP?

- What should be the state of the stack after a script execution? What is clean stack rule and why is it important? Is it a policy rule or consensus rule?

- What are the different components of the transaction? Discuss each of them briefly. Discuss the changes in transaction structure before and after segwit upgrade.

- Discuss the signature verification process for multisig. Why all multisig transactions have a dummy value (OP_0) at the beginning of the unlocking script? Why would fixing this be a hard fork?

- Discuss different Sighash types along with their usecases. Which part of the transaction is hashed in each sighash type?

- Why do we encode addresses in base58 instead of base64? Discuss advantages of bech32 over base58 encoding format. 

- What are different sources of transaction malleability and how did the segwit upgrade fix it?

## Week 5: Chapter 8 (P2SH) + Chapter 9 (Blocks)

- Why was P2SH proposed, and what were its benefits over bare complex scripts?

- How was P2SH activated, and when? Was it a soft fork or a hard fork?

- Describe briefly the P2SH script execution mechanism.

- Describe briefly the P2SH signature validation mechanism.

- Why does the P2SH script hash 160 bits instead of the regular 256 bits hashes? Can this have any security issues for P2SH scripts?

- What is a coinbase transaction, and why is it necessary? What are the limitations of data insertion in the coinbase scriptsig? What would happen if a block does not have a coinbase transaction?

- What data is included in a Block Header? Describe briefly the uses of each.

- Describe briefly the process of Proof Of Work Mining. Is it possible to create fake proof of work? Why is it called "Proof of Work"?

- What is PoW Target and Difficulty? How is the difficulty value represented in the block header? How are target and difficulty values related?

- What is the difficulty adjustment? Why is it required? What would happen if Bitcoin didn't have difficulty adjustment?

## Week 6: Chapter 10 (Networking) + Chapter 11 (SPV)

- Describe the structure of a `tx` message. What does the fields imply?

- Describe the process of network handshake. What information is propagated in the handshake message? Why is this information needed to establish a connection?

- Every network message has a different payload structure. You can refer to this [link](https://en.bitcoin.it/wiki/Protocol_documentation#Message_types) for a comprehensive list. Explain the payload structure in the `getheaders` message.

- Why is the parsed timestamp field from a version message 8 bytes (as opposed to 4 bytes in the block header)?

- What are the major network messages a node communicates among them? What is the biggest and the smallest network message?

- What is an SPV? Why is it useful? Do you know any real-life mobile app that uses SPV inside?

- What is a Merkle tree? Describe the process of finding the merkle root from a set of leaves.

- What does the Merkle tree data structure achieve in terms of provability? What parts of the Bitcoin protocol it is used?

- How is the Merkle tree data included in a block? What does a node use this data for?

## Week 7: Chapter 12 (Bloom Filters) + Chapter 13 (Segwit)

- Describe briefly what a bloom filter is and why it is useful.

- Explain the process by which light clients communicate for bloom filter support with full nodes. What is the difference in gossip messages for such light-client/full-node connections compared to regular P2P gossip?

- How do light clients finally find the relevant transactions from bloom filters?

- What are the problems associated with using a Bloom Filter for SPV? How are these problems solved in BIP157?

- Can you provide practical examples of wallets that use Bloom Filters? Additionally, what are some examples of BIP157 Filters?

- What was the major changes introduced in the Segwit upgrade? Why is it called Segregated Witness?

- Define transaction malleability. Explain how SegWit fixes transactional malleability. Why was it important to fix this issue?

- What are the two major SegWit address types, and what is the main difference between them?

- Explain the concept of a nested SegWit address. why was nested SegWit required?

- How was Segwit activated as a soft fork? How would non-segwit nodes process a Segwit transaction?

- The three broad categories of cryptographic algorithms are ==hash algorithms, symmetric cryptographic algorithms, and asymmetric cryptographic algorithms==.

==Symmetric== cryptographic algorithms use the same key to encrypt and decrypt the data. Data encrypted by Bob with a key can only be decrypted by Alice using that same key. Because the key must be kept private (confidential), symmetric encryption is also called private key cryptography.

![[Pasted image 20240201134949.png]]

Advanced Encryption Standard (AES). The Advanced Encryption Standard (AES) is a symmetric algorithm that performs three steps on every block (128 bits) of plaintext. Within step 2, multiple rounds are performed depending upon the key size: a 128-bit key performs nine rounds, a 192-bit key performs 11 rounds, and a 256-bit key, known as AES-256, uses 13 rounds. Within each round, bytes are substituted and rearranged, and then special multiplication is performed based on the new arrangement. To date, no attacks have been successful against AES.

Rivest Cipher (RC). Rivest Cipher (RC) is a family of six algorithms. RC4, the most common RC cipher, is a stream cipher that accepts keys up to 128 bits in length.

Blowfish. Blowfish is a block cipher algorithm that operates on 64-bit blocks and can have a key length from 32 to 448 bits. To date, no significant weaknesses have been identified. A later derivation of Blowfish known as Twofish is also considered a strong algorithm, although it has not been used as widely as Blowfish.

---
==Asymmetric== encryption uses two keys instead of only one. The keys are mathematically related and are known as the public key and the private key. The public key is known to everyone and can be freely distributed, while the private key is known only to the individual to whom it belongs.

### Several important principles regarding asymmetric cryptography are as follows:

- Key pairs. Unlike symmetric cryptography that uses only one key, asymmetric cryptography requires a pair of keys.

- Public key. Public keys, by their nature, are designed to be public and do not need to be protected. They can be freely given to anyone or even posted on the Internet.

- Private key. The private key must be kept confidential and never shared.

- Both directions. Asymmetric cryptography keys can work in both directions. A document encrypted with a public key can be decrypted with the corresponding private key. In the same way, a document encrypted with a private key can be decrypted with its public key.
---
The asymmetric algorithm ==RSA== was published in 1977 and became the basis for several products. The RSA algorithm multiplies two large prime numbers (a prime number is a number divisible only by itself and 1), p and q, to compute their product  . Next, a number e is chosen that is less than n and a prime factor to (p − 1)(q − 1). Another number d is determined so that (ed − 1) is divisible by (p − 1)(q − 1). The values of e and d are the public and private exponents. The public key is the pair (n,e) while the private key is (n,d). The numbers p and q can be discarded.

==Elliptic Curve Cryptography (ECC)==
The basis of RSA asymmetric encryption security is factoring, or the prime numbers that make up a value. As computers become faster and more powerful, the ability to “crack” RSA asymmetric encryption by computing the factoring has grown. Instead of using factoring as the basis, other research looked at an obscure (and esoteric) branch of mathematics called elliptic curves. In short, an elliptic curve is a set of points that satisfy a specific mathematical equation. Elliptic curves paved the way for a different form of asymmetric encryption not based on factoring.

Instead of using large prime numbers as with RSA, elliptic curve cryptography (ECC) uses sloping curves. An elliptic curve is a function drawn on an X-Y axis as a gently curved line. By adding the values of two points on the curve, a third point on the curve can be derived, of which the inverse is used, as illustrated in Figure 6-8. With ECC, users share one elliptic curve and one point on the curve. One user chooses a secret random number and computes a public key based on a point on the curve; the other user does the same. They can now exchange messages because the shared public keys can generate a private key on an elliptic curve.

==***Proof***== can be provided with asymmetric cryptography, however, by creating a _digital signature_, which is an electronic verification of the sender. A handwritten signature on a paper document serves as proof that the signer has read and agreed to the document. A digital signature is much the same but can provide additional benefits. A digital signature can

- _Verify the sender_. A digital signature serves to confirm the identity of the person from whom the electronic message originated.
    
- _Prevent the sender from disowning the message_. The signer cannot later attempt to disown it by claiming the signature was forged (nonrepudiation).
    
- _Prove the integrity of the message_. A digital signature can prove that the message has not been altered since it was signed.
    
The basis for a digital signature rests on the ability of asymmetric keys to work in both directions (a public key can encrypt a document that can be decrypted with a private key, and the private key can encrypt a document that can be decrypted by the public key).***Proof*** can be provided with asymmetric cryptography, however, by creating a digital signature, which is an electronic verification of the sender. A handwritten signature on a paper document serves as proof that the signer has read and agreed to the document. A digital signature is much the same but can provide additional benefits. A digital signature can

- Verify the sender. A digital signature serves to confirm the identity of the person from whom the electronic message originated.

- Prevent the sender from disowning the message. The signer cannot later attempt to disown it by claiming the signature was forged (nonrepudiation).

- Prove the integrity of the message. A digital signature can prove that the message has not been altered since it was signed.

The basis for a digital signature rests on the ability of asymmetric keys to work in both directions (a public key can encrypt a document that can be decrypted with a private key, and the private key can encrypt a document that can be decrypted by the public key).

![[Pasted image 20240201140126.png]]



---


Common hash algorithms include the following:

Message Digest (MD). One of the earliest hash algorithms is a “family” of algorithms known as Message Digest (MD). Versions of MD hashes were introduced over almost 20 years, from MD2 (1989) to MD6 (2008). The most widely used of these algorithms is MD5. This hash algorithm uses four variables of 32 bits each in a round-robin fashion to create a value that is then compressed. Serious weaknesses have been identified in MD5, and it is no longer considered suitable for use.

Secure Hash Algorithm (SHA). Another family of hashes is the Secure Hash Algorithm (SHA). SHA-1 was developed in 1993 but is no longer considered suitable for use. SHA-2 has six variations, the most common are SHA-256, SHA-384, and SHA-512 (the last number indicates the length in bits of the digest that is generated) and is currently considered a secure hash. In 2015, after eight years of competition between 51 original entries, SHA-3 was announced as a new standard. One design goal of SHA-3 was to make it dissimilar to previous hash algorithms to prevent threat actors from building on earlier work of compromising the algorithms.

RIPEMD. RIPEMD stands for RACE Integrity Primitives Evaluation Message Digest. The primary design feature of RIPEMD is two different and independent parallel chains of computation, the results of which are then combined at the end of the process. All versions of RIPEMD are based on the length of the digest created, including RIPEMD-128, RIPEMD-256, and RIPEMD-320.

![[Pasted image 20240201131648.png]]

- Pseudorandom Number Generator (PRNG), which is an algorithm for creating a sequence of numbers whose properties approximate those of a random number.

- What makes cryptography secure is the obscurity of the key and not of the algorithm.

- Another variation in cryptographic algorithms is the amount of data that is processed at a time. Some algorithms use a stream cipher that takes one character and replaces it with one character. Other algorithms make use of a block cipher. Whereas a stream cipher works on one character at a time, a block cipher manipulates an entire block of plaintext at one time. The plaintext message is divided into separate blocks of 8 to 16 bytes, and then each block is encrypted independently. For additional security, the blocks can be randomized. Recently, a third type called a sponge function has been introduced. A sponge function takes as input a string of any length and returns a string of any requested variable length. This function repeatedly applies a process on the input that has been padded with additional characters until all characters are used (absorbed in the sponge).

- 



# Public Key Encryption

- Cryptography is the science
- Encryption is the method - the process to transform cleartext into ciphertext
- Decryption - the process to transfrom encrypted text into clear text

## Key

- The key in a ecryption algorithm appers as a series of random `0` and `1` each one corresponding to a bit.
- The total number of bits in a key is known as the **key size**
- A 20 bit size key might look like: `0001 0101 1110 1100 0110`

## Symetric Encryption

Uses the same key to encrypt and decrypt the text making it faster but less secure.

In all symetric algorithms both sender and receiver need to have knowledge of the selected algorithm and key before hand.

> Is hard to break than asymetric

### Symmetric-key algorithm examples:

- **DES** - _First to be adopted. Developed in 1970_
- 3DES
- **AES** - _Replaced DES later on_
- IDEA
- CAST5
- Twofish
- Serpent
- Camellia
- Blowfish
- Kuznyechik
- Safer

## Asyncmetric Encryption

Also known as public key cryptography uses two keys: A public and a private key. Which one can encrypt and the other can decrypt

Does not require a key exchange. Both sender and receiver can generate a public/private key pair and share only the public key. If anyone wants to encrypt a message using my public key only my private key can decrypt that message.

### Public key generation

A private key can be used to generate public keys but not vice-version. It is a one-way operation similar to a hash function.

### Digital signature

A ciphertext encrypted with a public key can only be decrypted by is corresponding private key
A ciphertext encrypted with a private key also can only be decrypted by is corresponding public key

### Asymetric-key algorithm examples:

- Rivest Shamir Adleman (RSA) - _Oldest algorithm 1977_
- Elliptical Curve Cryptography (ECC) _Smaller and faster_

> Bitcoin uses Elliptic Curve Digital Signature Algorithm (ECDSA)

> Asymetric encryption is usually easier to break than a symmetric key but does not require key exchange

### Models to break encryption

**Chosen Plaintext Attack (CPA)**
Attacker send 2 messages to a computer to encrypt and tries to identify which is each

**Chosen Ciphertext Attack (CCA)**
Attacker send multiple encrypted messages to a computer to decrypt and tries to identify the private key based on the result

### Cryptographic Assumptions and Quantum Computing

Encryption schemas are based on matematical assumptions. The RSA assumes that computers today can't proccess enough to calculate every prime number to break the encryption before running out of resource.

But when quantum computers becomes available in the market **RSA encryption will be easily breakable**. Some quantum-safe asymetric encryption algorithms are being developed already, like the hash-based encryption method, which uses a larger key size than ECC.

The symmetric encryption based algorithms have several quantum-safe algorithms for example: AES-256 and Twofish-256

## Session key

To increase the security between sender and receiver a session key can be created.

1. Receiver generates a public/private keypair using asymetric encryption and sends the public key to the sender
2. Sender generates a key and encrypt using Receiver public key and sends back to the receiver
3. Receiver decrypt the encrypted key using the corresponding private key
4. Now both Sender and Receiver has a key that can be used to encrypt messages using symetric encryption

This method is used by browsers when comunicating via HTTPS

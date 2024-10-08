# Hash functions

Hash function is a type mathematical function that convert an arbitrary length data into a fixed-length output known as hash digest. **This process is not reversable.**

**The length of the hash, such as 256 bits, is set by the function**

- A bit is a binary value, `0` or `1`
- Hash digest are usually represented as hexadecimal texts
- The hash digest is a digital fingerprint of the original text

> ℹ️ Hexadecimal texts are composed by numbers from `0` to `9` and each digit higher than `9` is represented by letters from `A` to `F`

> ℹ️ In a hexadecimal text wach pair of letter corresponds to a group of 8 bits

Their use in blockchain

- Linking blocks
- Mining (solve a proof of work)
- Digital signatures

## Has function properties

**Preimage Resistance**

Means that the hash digest generated by a hash function must ensure the digest is not easily reversable

**Second Preimage Resistance and Weak Collision Resistance**

Must be dificult to discover what input is used to generate the same hash digest

> ℹ️ Called Weak Collision Resistance because in this scenario is used the same input to try to discover the same hash digest

**Collision Resistance**

Must be hard to find 2 inputs that generates the same hash digest

> ℹ️ The most hard property

> ℹ️ 256 bits hash function generates 2^256 possible outputs. So since 2ˆ256 is a finite number is theoretically possible to hash digests to collide

## MD5 and SHA

Examples of hash functions:

- Message Digest (MD)
- Secure Hash Function (SHA)
- RIPEMD
- Whirlpool
- Blake

**MD5**

was once a popular choice with a 128-bit hash value but it was proven to not be resistant to collisions in 2004 (not longer recommend)

**SHA**

The SHA family consists of:

- **SHA-0** - First published by National Institure of Standards and Technology in 1993 but lasted until 2004 when a collision attack was discovered
- **SHA-1** - Was also found a collision in 2005
- **SHA-2** - To this date none of the SHA-2 algorithms function (SHA-224, SHA-256, SHA-384, SHA-512) has reported collisions
- **SHA-3** - Produces a 512 bit and uses a algorithm caleld Keccak

> Bitcoin uses SHA-256

**RIPEMD**

Developed by the open research community has five functions:

- RIPEMD
- RIPEMD-128
- RIPEMD-160 (most used)
- RIPEMD-256
- RIPEMD-320

> Bitcoin uses RIPEMD-160 to generate addresses

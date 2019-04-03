
# L02, Symmetric-key Encryption

Basic Concept - Symmetric Key Encryption Schemes (SKES)
- M - Plaintext Space
- C - Ciphertext Space
- K - Key space
- family of encryption function: $E_k : M \rightarrow C, \forall k \in K$
- family of decryption function: $D_k : C \rightarrow M, \forall k \in K$

How to use SKES to achieve confidentiality
- parties agree on secret key $k \in K$ through **secured** channel
- computes $c = E_k(m)$ and sends `c` to Bob via unsecured channel
- use $m = D_K(c)$ to get original message

## Simple Substitution Cipher
- M = All English Messages
- C = All Encrypted Messages
- K = all permutations of English Alphabet
- $E_k(m)$ - Apply permutation $k$ to `m`, one letter at a time
- $D_k(m)$ - Apply permutation $k^{-1}$ to `m`, one letter at a time

What it means for SKES to be secure?
- what is the adversary's goal, what are their abilities, how do they interact with the parties

Security Model: Defines the computational abilities of the adversary and how they interact with the parties

Adversary Interactions:
- Passive Attacks
  - Ciphertext only attacks - know some cipher text
  - Known Plain Text attacks - knows the plaintext and cipher text

- Active Attacks
  - Chosen-plaintext attack: adversary can choose plaintext and obtain ciphertext

- Other
  - Cladestine attack: bribery, blackmail etc.
  - Side-channel attacks: monitor encryption and decryption equipment and attack the hardware (timed, electro-magnetic)

Computational Power of Adversary
- Information theoretic security: assume infinite resources
- Complex theoretic security: poly-time Turing machine
- Computational security: "computationally bounded" (huge advanced computer that we know)

If key is known or if they can recover plaintext from ciphertext, then SKES is **totally broken**
- learn partial information: **semantically secure**

### Secure SKES
If it is semantically secure against chosen-plaintext attack by computationally bounded adversary

Broken If: given ciphertext `c`, adversary chooses plaintexts and get ciphertexts, leading to learning information about ciphertext `c` (other than just length)

### Desirable SKES
- $E_k$ and $D_k$ should be efficient
- secret key should be small but effective
- scheme should be secure, even against designer of system

Simple Substitution is totally insecure against chosen-plaintext attack
- even cipher-text only can yield correct result if you test all permutation
- but this is infeasible as you would need $24!$ or $2^{88}$

#### Work Factor
- $2^{40}$ is very easy
- $2^{56}$ is easy
- $2^{64}$ is feasible
- $2^{80}$ is barely feasible
- $2^{128}$ is infeasible

Laudauer limit says that trying $2^{128}$ needs more power than that is that is produced

### Security Level
level $l$ if the fastest known attack on scheme takes $2^l$ operations
- security of 128 bits is desirable

Simple Substitution Cipher
- since frequency analysis of the ciphertext can be used to recover the key, the cipher is **totally** insecure

### Polyaphabetic Ciphers
Idea: several permutations, so a letter can be encrypted to one of many letters

## Vigenere Cipher
- choose a Key `k` that has no repeated letters
  - eg. k = CRYPTO, hence messages just add each letter at a time (loop) and modulo 26
- totally insecure against chosen plaintext (just give it all same letter)
- Also totally insecure against ciphertext-only attack

## Vernam - One-Time Pad
- Key - sequence of random letters, **as long as the plaintext**
  - must NOT be reused (or else you can figure out what has changed)


## Binary Messages
- assumes keys and message are always in binary form (bit strings)
  - XOR = Bitwise addition modulo 2

XOR properties




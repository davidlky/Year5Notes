## Day 1, 1/7

Cryptography is about securing communication in the presence of *malicious* activities

Fundamental Goals:
- Confidentiality: only those who should see it gets to see it
- Data Integrity: data should not be altered
- Data Origin Authentication: the source is the real source
- Non-repudiation: Prevent denying previous commitments

Secure Web Transactions
- SSL (Secure Socket Layer)
  - Assures *client* the authenticity of *server* and establishes a secure channel for rest of session
- Symmetric Key Crypto: client and server shares a secret key `k`
  - engage in secure conversation through encryption via `AES`
  - authenticate ciphertexts with `HMAC`
- Public Key Cryptography
  - parties share *authenticated* but non-secret information
  - client selects a *secret session key* and encrypt with the public RSA key of the server, only server can then decrypt with its private key
  - To ensure you are getting the server's RSA keys, you trust a CA (certifying agent) to sign it
    - verify with by using the CA's RSA key that is in browser

- Points of Failure, human error and also NSA
  - Crypto usually not the weakest link, but catestrophic if broken


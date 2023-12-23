## Hashing
- It's a process of converting input data (often called a message) into a fixed-length string of characters, which is typically a sequence of numbers and letters. 
- The output, known as the hash value or hash code, should be unique to the input data.
- Used in data integrity verification, password storage, and [[General#Digital Signature|digital signatures]].

### SHA Hashing
- It specifically refers to algorithms from the SHA (Secure Hash Algorithm) family, which are cryptographic hash functions designed to be secure.

#### SHA-1 Hashing
- Vulnerabilities were discovered in SHA-1, making it susceptible to collision attacks where different inputs could produce the same hash value.
- Due to these vulnerabilities, SHA-1 is now considered depricated for security-sensitive applications.

- It is developed by the National Security Agency (NSA).

- It creates the fixed output size of 160 bits (20 bytes).

#### SHA-2 Hashing
- SHA-2 is considered secure and widely used for cryptographic applications, including digital signature and certificates.

- It consists of multiple hashing functions with varying output sizes, providing a range of security level.

- Output size varies depending on the hashing function (SHA-225, SHA-384, SHA-512, SHA-512/224, SHA-512/256) being used from 224 bits to 512 bits.

#### SHA-3 Hashing
- Unlike SHA-1 and SHA-2, SHA-3 is based on a different underlying structure known as the **Keccak sponge construction**. 
- It offers a different design philosophy compared to SHA-2.

- SHA-3 is the lastest member of the SHA family, designed as a response to advances in cryptanalysis and to provide an alternative to SHA-2.
- It was selected through a public competition organized by the National Institute of Standards and Technology (NIST).



## Digital Signature


## Bencode

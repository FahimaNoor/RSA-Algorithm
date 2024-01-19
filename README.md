# RSA-Algorithm
## Part 1: Simple RSA (Encryption and Decryption)
RSA is a asymmetric public-key encryption algorithm. In RSA, d is private key. e and N are public keys. Any two parties willing to communicate with each other will need to use these keys. Messages will be encrypted using the public keys of the partner. However, the message can only be decrypted using the private key of the intended receiver and no one else.

### RSA Key Generation:

  1. Two large prime numbers p and q are randomly generated.
  2. N is calculated using *N=pq*.
  3. phi_N calculated using *phi_N=(p-1)(q-1)*.
  4. Public key e is generated such that it is not a factor of phi_N.
  5. Private key d calculated using d=e^-1 mod phi_N


### RSA Enecryption:
The messages are encrypted for the partner using the following formula: *Encrypted_Message = PlainText^e mod N* , where e and N are the public key of the partner to whom the cipher text will be send to.

### RSA Decryption:
The messages are decrypted using the following formula: *Decrypted Message = Encrypted_Messaget^d mod N*, where e and N are the public key of the partner who received the cipher text (Encrypted_Message). To decrypt the ciphertext that obtained from my partner, I will use my private key d and my public key N.

## Part 2: RSA Digital Signature Scheme
Signature Scheme is needed to ensure that they are receiving data from the corrrect person. (Hash function is not used in this part). For this project, the overall working process of the scheme is as follows:
  1. Both partners will create a signature on their messages using *S=M^d mod N*.
  2. They will share the message(M) and the corresponding signature(S).
  3. Partners will then verify the validity of the signature by computing *M1=S^e mod N* on their partner's signature. If the M1 matches the message(M) send by their partner then it can be said that the signature is valid.

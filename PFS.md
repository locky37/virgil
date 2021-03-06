# Perfect Forward Secrecy

The security of communications transmitted across the Internet can be improved by using public key cryptography. However if the public and private keys used in those communications are compromised it can reveal the data exchanged in that session as well as the data exchanged in previous sessions.

Perfect Forward Secrecy (PFS) Is a technique, that protects previously intercepted traffic from being decrypted even if the main private key is compromised. With PFS enabled communication, a hacker could only access information that is actively transmitted because PFS forces a system to create different keys per session. In other words, PFS makes sure there is no master key to decrypt all the traffic.

In PFS you use Diffie-Hellman's algorithms, where the master key is used. After the parameters for the algorithm are agreed on, the key exchange takes place using those parameters, and a secret of both parties. The parameters are not secret, and the secrets the parties used are discarded after the session key is established. This way if you discover the master key you can't discover the session key.

![PFS](https://github.com/VirgilSecurity/virgil/blob/master/images/PFS.png)



### Bob side (receiver)
Before Bob can use PFS he must do the following:

1. Have a main key pair (identity)
2. Generate an ephemeral key pair, sign it with the main key


### Alice side (sender)

1. Have a main key pair (her identity)
2. Generate an ephemeral key pair, sign it with the main key
3. Get Bob's identity, ephemeral public key

### Conclusion

PFS is important while dealing with sensitive data because it adds an extra layer of security. With PFS, the session key is derived from input of both parties and not transmitted through the Internet. Furthermore, it is freshly generated for each session.

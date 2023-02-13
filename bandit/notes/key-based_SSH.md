Public key authentication is more secure than password authentication. This is particularly important if the computer is visible on the internet. 

With public key authentication, the authenticating entity has a public key and a private key. Each key is a large number with special mathematical properties. The private key is kept on the computer you log in from, while the public key is stored on the `.ssh/authorized_keys` file on all the computers you want to log in to. When you log in to a computer, the SSH server uses the public key to "lock" messages in a way that can only be "unlocked" by your private key - this means that even the most resourceful attacker can't snoop on, or interfere with, your session.

As an extra security measure, most SSH programs store the private key in a passphrase-protected format, so that if your computer is stolen or broken in to, you should have enough time to disable your old public key before they break the passphrase and start using your key.

Public key authentication is a much better solution than passwords for most people. In fact, if you don't mind leaving a private key unprotected on your hard disk, you can even use keys to do secure automatic log-ins - as part of a network backup, for example. Different SSH programs generate public keys in different ways, but they all generate `public keys` in a similar format:
```text
<ssh-rsa or ssh-dss> <really long string of nonsense> <username>@<host>
```

when you want to log into a remote system using SSH, the remote system will use your public key to verify your identity. If the verification is successful, the remote system will allow you to log in without asking for a password.

OpenSSH is a suite of network-level utilities based on the Secure Shell (SSH) protocol, which includes tools for securely accessing remote systems, transferring files, and running remote commands. **Key-based authentication** is one of the authentication methods supported by the SSH protocol, and is an alternative to **password-based authentication**.

OpenSSH provides support for key-based authentication as well as several other authentication methods, such as password-based authentication and host-based authentication. The choice of authentication method depends on the specific requirements and security needs of the system and the user.

The most commonly used algorithms for key-based authentication are:

1. RSA (Rivest-Shamir-Adleman): the only recommended choice for new keys
2. DSA (Digital Signature Algorithm): has come to be seen as less secure in recent years
3. ECDSA (Elliptic Curve Digital Signature Algorithm): ECDSA is a variant of the Digital Signature Algorithm (DSA) that uses elliptic curve cryptography. ECDSA provides the same security as DSA with shorter key lengths, making it a popular choice for Internet protocols.
4. Ed25519: Ed25519 is a new digital signature algorithm that is faster and more secure than other algorithms. It is widely used in modern SSH implementations and provides strong security with a small key size.

## SSH key generation
```bash
mkdir ~/.ssh
chmod 700 ~/.ssh
ssh-keygen -t rsa
```
```bash
Generating public/private rsa key pair.
Enter file in which to save the key (/home/kali/.ssh/id_rsa): rsa_key
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in rsa_key
Your public key has been saved in rsa_key.pub
The key fingerprint is:
```

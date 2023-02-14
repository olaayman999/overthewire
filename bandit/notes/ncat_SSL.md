Ncat can encrypt its traffic using SSL. In connect "client" mode, simply add the `--ssl` option. `--ssl` works with TCP (the default) and SCTP using `--sctp`

```bash
ncat -C --ssl <server> <port>
```
uses the `ncat` command to establish an encrypted connection to a remote server using SSL (Secure Sockets Layer) encryption, The `-C` and `--ssl`  are both used to specify that the connection should be encrypted using SSL. However, they are used with different versions of the `ncat` utility.

`-C` is used with older versions of the `ncat` utility, while `--ssl` is used with newer versions. The exact behavior of these options may vary depending on the version of ncat you are using.

Sometimes an SSL server will require a client certificate for authentication. When this is the case, use the `--ssl-cert` and `--ssl-key` options to **give the locations of PEM-encoded files containing the certificate and private key**, respectively. The certificate and key may be in the same file.

By default the** client will not do any server certificate verification**, so it will not be detected if the server has the wrong certificate or no certificate at all. Use the `--ssl-verify` option to require verification of the certificate and matching of the domain name.

```bash
ncat -C --ssl-verify <server> <port>
```

Verification is done using the `ca-bundle.crt` certificate bundle shipped with Ncat, plus whatever trusted certificates the OS may provide. If you want to verify a connection to a server whose certificate isn't signed by one of the default certification authorities, use the `--ssl-trustfile` to name a file containing certificates you trust.** The file must be in PEM format.**

```bash
ncat -C --ssl-verify --ssl-trustfile <custom-certs.pem> <server> <port>
```

Verification should be done whenever it is feasible. Even with encryption, an unverified connection is vulnerable to a man-in-the-middle attack. Ncat does not do certificate revocation checking.

SSL connections depend on the client and server _agreeing on a common ciphersuite_: a combination of key exchange, symmetric cipher, and message integrity mechanism. The choice of which ciphersuites to offer (as a client) or accept (as a server) is a matter of choice between the greatest compatibility and the greatest security. The default set, expressed as an **OpenSSL** cipherlist, is `ALL:!aNULL:!eNULL:!LOW:!EXP:!RC4:!MD5:@STRENGTH`, a reasonable balance between the two ends of the spectrum. To set a different priority or initial choice, use the --ssl-ciphers option.
```bash
      ncat --ssl-ciphers <HIGH:!aNULL:!eNULL> <server> 443
```

Ncat can act as an SSL server as well. The server must provide a certificate that clients can verify if they choose. If you start an SSL server without using the `--ssl-cert` and `--ssl-key` options, Ncat will automatically generate a certificate and 2,048-bit RSA key. The certificate will of course not be trusted by any application doing certificate verification. In verbose mode, the key's fingerprint will be printed so you can do manual verification if desired.

---
layout: default
---

# How to Enable SSL on NetWeaver Application Server

- `SSF02` SSF Test Program
- `SMICF` ICM Monitor `Goto -> Trace File -> Display End`
- `RZ10` Edit Profiles

```
16.04.2018                                                                                           abapGit Test SSL                                                                                                  1
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Error Number     1
Error message: SSL handshake with github.com:443 failed: SSSLERR_SSL_READ (-58)
SAPCRYPTO:SSL_read() failed

SapSSLSessionStartNB()==SSSLERR_SSL_READ
  SSL:SSL_read() failed  (536875120/0x20001070)
  => "received a f
Also check transaction SMICM -> Goto -> Trace File -> Display End
```

```
Over the course of year 2016, a growing number of TLS servers were reconfigured to abort/reject TLSv1.0 handshakes, or they are requring forward secrecy (PFS) cipher suites for access. The currently recommended settings for TLSv1.2 interoperability are (requiring at least CommonCryptoLib 8.4.38, recommending at least 8.4.49):

        ssl/ciphersuites           =  135:PFS:HIGH::EC_P256:EC_HIGH
 
        ssl/client_ciphersuites  =  150:PFS:HIGH::EC_P256:EC_HIGH
 
For a SAP Solution Manager System 7.[012], please use the following value for ssl/client_ciphersuites instead:

        ssl/client_ciphersuites = 918:PFS:HIGH::EC_P256:EC_HIGH
```
*Source: [SAP Note 510007](https://launchpad.support.sap.com/#/notes/510007)*

## References

- [SAP Note 510007](https://launchpad.support.sap.com/#/notes/510007)
- [TLS 1.2 Support in SAP - SCN](https://archive.sap.com/discussions/thread/3751351)

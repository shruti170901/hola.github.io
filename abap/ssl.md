---
layout: default
---

# How to Enable SSL on NetWeaver Application Server

## 1. Install Client Certificates

1) Open website you want to connect to e.g. [github.com](https://github.com/) with your browser

2) [Export all client certificates in the chain with your browser](export-certs-with-browser)

3) Go to transaction `STRUST`

4) Double click node `SSL Client (Anonymous)`

5) Import certificate exported from 2)

6) Add to Certificate List

7) Repeat until all certificates are added

8) Save

## 2. Test SSL Connection

1) Create a new ABAP program `ZABAPGIT_TEST_SSL` and copy source code from [here](https://github.com/larshp/abapGit/blob/master/docs/other-test-ssl.md)

2) Run the program and try to connect

3) If you see `Success, it works` then you're good.  

If you see error something like below, please see the next section.

```
Error Number     1
Error message: SSL handshake with github.com:443 failed: SSSLERR_SSL_READ (-58)
SAPCRYPTO:SSL_read() failed

SapSSLSessionStartNB()==SSSLERR_SSL_READ
  SSL:SSL_read() failed  (536875120/0x20001070)
  => "received a f
Also check transaction SMICM -> Goto -> Trace File -> Display End
```

## 3. Check Trace File

1) Go to transaction `SMICF`

2) Go to menu `Goto -> Trace File -> Display End`

3) If you see message complaining about TLS version then proceed the next section

## 4. Enable TLS v1.2

1) Go to transaction `RZ10`

2) Open `DEFAULT` profile, select `Extended maintenance` and click `Change`

3) Add these two parameters:

```
Over the course of year 2016, a growing number of TLS servers were reconfigured to abort/reject TLSv1.0 handshakes, or they are requring forward secrecy (PFS) cipher suites for access. The currently recommended settings for TLSv1.2 interoperability are (requiring at least CommonCryptoLib 8.4.38, recommending at least 8.4.49):

        ssl/ciphersuites           =  135:PFS:HIGH::EC_P256:EC_HIGH
 
        ssl/client_ciphersuites  =  150:PFS:HIGH::EC_P256:EC_HIGH
 
For a SAP Solution Manager System 7.[012], please use the following value for ssl/client_ciphersuites instead:

        ssl/client_ciphersuites = 918:PFS:HIGH::EC_P256:EC_HIGH
```
*Source: [SAP Note 510007](https://launchpad.support.sap.com/#/notes/510007)*

4) Click `Copy` and Save

5) Restart server

6) Go back `SMICF` and see trace file again. If you see something like beloe then it means the paramaters are configured properly.

```
[Thr 139810885523200] =================================================
[Thr 139810885523200] = SSL Initialization    platform tag=(linuxx86_64_gcc43)
[Thr 139810885523200] =   (753_REL,Aug 18 2017,mt,ascii-uc,SAP_UC/size_t/void* = 16/64/64)
[Thr 139810885523200] =       resulting Filename = "/usr/sap/NPL/D00/exe/libsapcrypto.so"
[Thr 139810885523200] =   disabled FIPS 140-2 crypto kernel
[Thr 139810885523200] =   found CommonCryptoLib 8.5.14 (Jul 27 2017) [AES-NI,CLMUL,SSE3,SSSE3]
[Thr 139810885523200] =   current UserID: "npladm",  env-var USER="npladm"
[Thr 139810885523200] =   found SECUDIR environment variable
[Thr 139810885523200] =   using SECUDIR=/usr/sap/NPL/D00/sec
[Thr 139810885523200] = [dpf] ssl/ciphersuites=135:PFS:HIGH::EC_P256:EC_HIGH
[Thr 139810885523200] =   NOT creating Envvar SAPSSL_CIPHERSUITES=135:PFS:HIGH::EC_P256:EC_HIGH
[Thr 139810885523200] = [dpf] ssl/client_ciphersuites=150:PFS:HIGH::EC_P256:EC_HIGH
[Thr 139810885523200] =   NOT creating Envvar SAPSSL_CLIENT_CIPHERSUITES=150:PFS:HIGH::EC_P256:EC_HIGH
[Thr 139810885523200] = Success    SapCryptoLib SSL ready!
[Thr 139810885523200] =================================================
```

7) Test SSL connection again and it should be okay now


## References

- [SAP Note 510007](https://launchpad.support.sap.com/#/notes/510007)
- [TLS 1.2 Support in SAP - SCN](https://archive.sap.com/discussions/thread/3751351)

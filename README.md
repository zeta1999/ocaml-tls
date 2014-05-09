ocaml-tls
==========

TLS 1.0, TLS 1.1, and TLS 1.2 support in pure OCaml.

status
======

Client and server side are working. At least the lwt backend (echo_client / http_client / echo_server / test_server). Mirage API currently under reconstruction.

You can pass ``openssl s_server`` a ``-cipher`` argument (following values work at the moment: ``DHE-RSA-AES256-SHA AES256-SHA DHE-RSA-AES128-SHA AES128-SHA AES128-SHA EDH-RSA-DES-CBC3-SHA DES-CBC3-SHA RC4-SHA RC4-MD5``.

implemented

- RFC 2246 - TLS Protocol version 1.0
- RFC 3268 - AES Ciphersuites for TLS
- RFC 4346 - TLS Protocol version 1.1
- RFC 4366 - TLS Extensions (notably Server Name Indication - SNI)
- RFC 5246 - TLS Protocol version 1.2
- RFC 5746 - TLS Renegotiation Indication Extension
- draft-agl-tls-padding-03 - A TLS padding extension

work in progress

- RFC 6520 - TLS Heartbeat extension
- RFC 4492 - Elliptic Curve Cryptography Ciphersuites for TLS

trusted code base
=================

- this library
- cstruct https://github.com/avsm/ocaml-cstruct
- crypto from https://github.com/mirleft/ocaml-nocrypto (using C implementations of symmetric ciphers and hashes)
- zarith from https://forge.ocamlcore.org/projects/zarith/ (which interfaces libgmp https://gmplib.org/)
- asn.1 parser combinator from https://github.com/pqwy/ocaml-asn1-combinators
- OCaml runtime
- operating system
- hardware
- OCaml compiler

ciphersuites
============

key exchange
- DHE_RSA
- RSA

encryption
- 3DES
- AES_128
- AES_256
- RC4_128

mac
- MD5
- SHA1
- SHA256
- SHA384
- SHA512

TODO (before any deployment)
============================

- address all [security concerns](https://github.com/mirleft/ocaml-tls/issues?labels=security+concern&page=1&state=open) in a convincing way
- fix config (currently Flow.default_config and Server.default_server_config)
- bits and pieces from useful extensions (heartbeat)

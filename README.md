# Any Server May Ask

**knell**

Timestamp of record (archive.org): https://archive.org/details/knell-any-server-may-ask

Matrix is presented as a federated network: no single operator, no central point of trust. A read of the code that ships today shows where the trust actually pooled. By the Foundation's own figures, matrix.org holds 370,000 of the network's 1,150,000 monthly active users — roughly a third of the "decentralized" network on one operator's server. Synapse also ships with matrix.org as the default trusted key server for every other server's signing keys, with no notary signature configured to check — the trust is TLS-only. Every cross-signing key a user has, plus the key that decrypts their entire backed-up history, sits in one store under a single passphrase-derived key whose parameters and a known-plaintext check value are stored on the homeserver — so the homeserver can brute-force that passphrase entirely offline. And media uploaded into a private room can be fetched by any other homeserver on the network, with no room-membership check — proven live between two instances of the pinned release: byte-identical file, delivered to a server that had no business asking.

## Verify

```
gpg --import knell-public.asc
gpg --verify paper-matrix-FINAL-2026-11-04.md.asc
```

Expect: `Good signature from "knell"`, key 133883AB9F6EDE5B9BA6B82E27BEDAF0CE152F25
Fingerprint: 1338 83AB 9F6E DE5B 9BA6 B82E 27BE DAF0 CE15 2F25

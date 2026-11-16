# Nyx Byte

Bitcoin infrastructure. Indexes, protocols, live systems.

I build the part that sits under a wallet, an explorer or an analytics product:
own chainstate indexes instead of third-party APIs, so answers come in
microseconds and keep coming when someone else's API is down.

**[nullbytexx.github.io](https://nullbytexx.github.io)**

---

### What I work on

| area | detail |
|---|---|
| Chain indexing | UTXO set → compact on-disk index, memory-mapped, one B-tree descent per query |
| Protocols | binary framing instead of JSON where throughput matters |
| Services | HTTP for humans, binary for machines, same index behind both |
| Operations | systemd units that survive reboot, network loss and dead peers |
| Cryptography | secp256k1, BIP32/39/44/49/84/86, bech32, verified against official vectors |

### Numbers from the current build

```
430 MB   index on disk for 55 000 000 records (mmap, resident set ~0)
525 k/s  lookups per core over that index
80 270/s addresses answered in batches of 10 000
402 µs   single address, HTTP stack included
```

### Stack

```
Python 3.12    sqlite3, mmap, multiprocessing, asyncio-level HTTP
Bitcoin Core   full node, prune, RPC, P2P
SQLite         WITHOUT ROWID, BLOB keys, PRAGMA tuning
Linux          systemd Type=simple/oneshot, timers, sandbox, ProtectSystem
Network        1 Gbit LAN, ssh, iperf3, latency percentiles
```

### How I work

Measure first, then change. Every number above came from a benchmark, and every
fix in the operational layer came from watching something fail: a 41 ms lookup
that was Nagle and delayed ACK, a peer set that looked full but delivered
nothing, a sandbox that silently blocked a logger.

---

<sub>Available for contract work. Open an issue on any repository or write to the address on the profile.</sub>

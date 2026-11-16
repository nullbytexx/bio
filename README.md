# Nyx Byte

Bitcoin infrastructure. Indexes, protocols, live systems.

**→ [nullbytexx.github.io](https://nullbytexx.github.io)**

`Bitcoin Core` · `SQLite` · `mmap` · `systemd` · `Linux` · `1 Gbit`

---

## What I do

I build the layer under a wallet, an explorer or an analytics product: own
chainstate indexes instead of third-party APIs, so answers come in microseconds
and keep coming when someone else's API is down.

A full node validates the chain. Everything above that — knowing what is on an
address, answering a hundred thousand of those questions a second, staying up
while the network around it misbehaves — is work that has to be built on top.
That is what this repository is: the page, the numbers, the record of how they
were measured.

## Numbers

```
430 MB   index on disk for 55 000 000 records, memory-mapped
525 k/s  lookups per core over that index
80 270/s addresses answered in batches of 10 000
402 µs   single address, HTTP stack included
```

Every one of these came from a benchmark on real hardware, not an estimate.

## How I work

Measure first, then change. The fixes in the operational layer all came from
watching something fail and finding out why: a 41 ms lookup that turned out to be
Nagle and delayed ACK, a peer set that looked full but delivered nothing, a
sandbox that silently blocked a logger.

## This repository

It holds two things, because they belong together:

- `index.html` — the page itself, one static file, no build step, no dependencies
- `.github/workflows/pages.yml` — deployment to GitHub Pages through Actions

The profile text you are reading is the `README.md` in the same place. There is
no separate profile repository: one account, one place for the record.

## Elsewhere

Nothing public at the moment. Work in progress stays private until it holds up.

---

<sub>Nyx Byte — available for contract work. Write to the address on the profile.</sub>

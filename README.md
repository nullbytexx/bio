# Nyx Byte

Bitcoin infrastructure. Indexes, protocols, live systems.

**→ [nullbytexx.github.io](https://nullbytexx.github.io)**

---

`Python 3.12` · `Bitcoin Core` · `SQLite` · `mmap` · `systemd` · `Linux`

I build the layer under a wallet, an explorer or an analytics product: own
chainstate indexes instead of third-party APIs, so answers come in microseconds
and keep coming when someone else's API is down.

```
430 MB   index on disk for 55M records, memory-mapped
525 k/s  lookups per core over that index
80 270/s addresses answered in batches of 10 000
402 µs   single address, HTTP included
```

Measure, then change. Every number above came from a benchmark, and every fix in
the operational layer came from watching something fail.

---

<sub>The page itself is `index.html`; publishing is handled by `.github/workflows/pages.yml`.</sub>

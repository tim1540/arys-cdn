# arys // cdn-relay

<div align="center">
  <img src="https://arysm4a.qzz.io/icon.jpg" width="100" height="100" style="border-radius: 50%;" alt="arys logo" />
  <p><b>High-availability decentralized static media distribution node for the <a href="https://arysm4a.qzz.io">arysm4a.qzz.io</a> ecosystem.</b></p>
</div>

---

### // OVERVIEW

This repository acts as an automated, zero-egress-fee static asset CDN (Content Delivery Network) for the **Arys Hub** core. It is dynamically managed by the server's backend (`core.js`) via the GitHub REST API and globally cached at the edge using **jsDelivr**.

By decoupling heavy media assets from the primary application server, we achieve:
* **0ms local disk overhead** on the hosting provider for public assets.
* **Ultra-fast global delivery** with sub-millisecond response times.
* **Aggressive edge caching** and automated synchronization.

---

### // ARCHITECTURE

```text
  [ Client Browser ] <==== (HTTPS/CDN) ====[ jsDelivr Edge ]
          ^                                       ^
          || (Interactive UI)                     || (Automated Sync)
          v                                       ||
   [ Arys Hub Core ] ===== (Public Uploads) ======> [ This Repository ]
          ||
          || (Private Uploads)
          v
   [ Local Storage ] (Zero-Trust Isolation)

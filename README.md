# Packets, Paths and Labels

A networking guide that works downward — from the WAN, through one network, through the
segmentation that divides a wire, down to the kernel on a single host.

**Read it → https://dharmjit.github.io/networking-learnings/**

One self-contained HTML file. No build step, no framework, no dependencies — the only
script drives the contents rail, section folding, the glossary tooltips, and
the convergence walk-through in section 07.
Every diagram is hand-authored inline SVG. The only external request is to Google Fonts.

## What's in it

**Origins** — who introduced each protocol, when, and what problem they actually had.

| Part | Sections |
| --- | --- |
| **I · Between networks** | 01 The shape of it · 02 The family tree · 03 BGP · 04 MPLS · 05 One address, many tenants · 06 Sessions all the way down |
| **II · Inside one network** | 07 Distance vector vs link state · 08 Bookkeeping · 09 Inside one router · 10 Quick reference |
| **III · One wire, many networks** | 11 VLAN · 12 VXLAN · 13 EVPN control plane |
| **IV · When the network becomes software** | 14 Virtual Ethernet · 15 Network namespaces · 16 VRF on Linux · 17 Identity, not address |
| **V · A datacentre, end to end** | 18 A neocloud, built — 128 GPU nodes, 16 storage nodes, fifteen racks, four fabrics |
| **Coda** | One idea, five times |

The through-line: give each tenant its own table, and make the identifier travel with the
packet. MPLS does it with a VPN label, VXLAN with a VNI, VLAN with twelve bits, the kernel
with a namespace — and it is the same idea every time.

## Reading it locally

```bash
open index.html
```

That is genuinely all. If you prefer a server:

```bash
python3 -m http.server -d . 8000
```

## Hosting your own copy

GitHub Pages, no workflow needed: **Settings → Pages → Source: Deploy from a branch →
`main` / `(root)`**. It is equally happy on Cloudflare Pages, Netlify, S3, or any static host.

If you fork it, update `og:url` and `link[rel=canonical]` in `index.html`, and the link above.

## Still to come

`bridge & FDB` · `conntrack & NAT` · `tc, qdiscs & XDP` ·
`NIC queues & offloads` · `RDMA & kernel bypass` · `MACsec & 802.1X`

## Corrections

Networking is a field of load-bearing "it depends", and this guide chooses one answer
where a real network might choose another. Two conventions:

- Administrative distances and timer defaults are **Cisco's** where they are vendor-specific.
- Kernel behaviour describes **Linux ≥ 5.10**.

If something here is wrong, a PR or an issue naming the RFC is very welcome.

## License

[CC BY 4.0](LICENSE) — use it, remix it, teach from it, keep the attribution.

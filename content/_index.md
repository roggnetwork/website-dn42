+++
title = 'rogg · dn42'
+++

## rogg on dn42

**rogg** is a network on <a href="https://dn42.dev/" target="_blank" rel="noopener">dn42</a>, the decentralized peer-to-peer network, running [bgpgg](https://www.roggnetwork.com/doc/) — rogg's own BGP daemon — across two points of presence.

| | |
|-------|---------------------------------|
| AS    | AS4242423930                    |
| IPv4  | 172.23.211.0/27                 |
| IPv6  | fd0d:fbde:bca5::/48             |
| POPs  | SEA1 (us-west-2) · CMH1 (us-east-2) |

SEA1 is the dn42 edge: it holds an eBGP session to an upstream carrying the full dn42 table (~2,300 routes). CMH1 reaches dn42 through SEA1 over iBGP. Both run bgpgg on AWS.

## Peering

rogg is open to peering.

- **Transport:** WireGuard, BGP over the IPv6 link-local pair.
- **Families:** MP-BGP — IPv4 and IPv6 unicast.
- **Policy:** we announce only our own aggregates and accept anything inside dn42's ranges. We are not transit.

To peer, open an issue at <a href="https://github.com/roggnetwork" target="_blank" rel="noopener">github.com/roggnetwork</a> with your ASN, WireGuard public key, and endpoint, and we'll reply with ours.
<!-- TODO: confirm the peering contact/channel — GitHub issues is a placeholder. -->

## Dashboards

Live per-POP telemetry, straight from bgpgg's Prometheus metrics: [SEA1](/dashboards/sea1/) · [CMH1](/dashboards/cmh1/).

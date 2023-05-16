---
title: "Pi-Hole + NextDNS Weirdness"
date: 2023-05-15T21:15:35-04:00
---

I have redunant Pi-Holes with NextDNS as the upstream DNS provider. I was encountering a problem recently where YouTube and various other Google services failed to load while connected to Tailscale and on my home network. If I disconnect from my home network, it started working again. If I remained connected to my home network and disconnected from Tailscale, it worked. All very puzzling.

After a lot of trial and error, I narrowed down the problem to some sort of DNSSEC weirdness. If I enable DNSSEC validation on the Pi-Hole, everything works fine. I'm not entirely sure why it behaves like this, but there it is.
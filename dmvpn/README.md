# Dynamic Multipoint VPN
These configurations represent the hub and spoke templates for a DMVPN Phase 3 deployment They are kept as simple and as broad as possible using highly secure authentication and encryption algorithms combined with a pre-shared key (PSK). You may decide to constrain the IKEv2 profile/keyring match criteria, the ACL permit statements, or any other tunable item. Users only need to find/replace the following IP addresses, along with the PSK, within the files:
  - Hub underlay: 203.0.113.1
  - Hub overlay: 192.0.2.1
  - Spoke underlay: 203.0.113.2
  - Spoke overlay: 192.0.2.2
  - Default PSK: SECRET123

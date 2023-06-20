# Quality of Service (QoS) Reference Configurations
These templates will help you deploy QoS in your network and are well-documented, easily modified, and known-good. These policies are based on matching Differentiated Services Code Point  DSCP) values and support both IPv4 and IPv6.

The following topology is used: `SENDER---QOS_ROUTER---RECEIVER`

Follow these steps to implement your desired template:

  1. Choose your classification style, either strictly RFC-4954 compliant (`cmap_rfc4594.txt`) or Cisco-modified (`cmap_cisco_mod.txt`). The only difference between these files is that DSCP values CS3 and CS5 are swapped. The relevant class-map descriptions also indicate this swap using `(CISCO MOD)` for clarity.

  2. Choose your queueing style. The number before the capital "Q" represents the number of queues in the policy-map. These policies may introduce intermediate class-maps to aggregate the atomic class-maps (defined in the previous step) for queuing purposes. These policy-specific class-maps are included in the corresponding `pmap_*q_config.txt` files.

  3. Apply your queuing policy in the output direction under the desired interface using the `service-policy output PMAP_QUEUE` syntax.

  4. To simplify QoS testing, I have included IP SLA configuration and verification snippets in the `test/` directory. These are used to configure the `SENDER` and `RECEIVER` routers. View the corresponding `README.md` for details.

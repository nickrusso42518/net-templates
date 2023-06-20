# QoS Testing and Verification
When designing a QoS policy, you don't need fancy software or extensive interaction to verify the policy's logic. Such tools and efforts may be required to perform production grade load testing, but first, I recommend ensuring the right traffic is being matched in the right places and receiving the right QoS treatment.

You can apply the IP Service Level Agreement (SLA) sender configuration on one device then configure the receiver to respond to those synthetic probes. I have pre-built a different probe for every unique DSCP value matched within the atomic class-maps, which simplifies testing. You can use basic find/replace functionality to replace the source and destination IP addresses.

These probes use a mix of TCP, UDP, and ICMP. Note that the operation identifier for each probe is equal to the decimal dscp value of the traffic being sent. The only exception is that DSCP DF (CS0) traffic uses operation ID 1. Also, note that IP SLA requires that the probe's QoS value be specified using the 8-bit Type of Service (ToS) format rather than the 6-bit DSCP format. In this way, the ToS value is always 4 times the operation ID.

The verification files indicate my recommended `show` commands to quickly verify whether the IP SLA probes are functional. If the probes are functional, you should see the appropriate matches under your applied QoS policy. If you are new to QoS or are designing a brand new policy, I suggest configuring one probe at a time, verifying its behavior individually, then moving on to the next probe.

# Week12 

chapter 5

## P12

> Describe how loops in paths can be detected in BGP.

The loops in the BGP (Border Gateway Protocol) can be detected as follows:

- The BGP protocol propagates and obtains reachability of all the neighboring AS (Autonomous Systems).
- The attributes AS-PATH and NEXT-HOP are used for routing.
- The router verifies all the AS numbers. If it finds its own number, it will discard the advertisement to prevent the looping. In this way BGP detects the loops and prevents them.

## P16

> Consider the following network. ISP B provides national backbone service to regional ISP A. ISP C provides national backbone service to regional ISP D. Each ISP consists of one AS. B and C peer with each other in two places using BGP. Consider traffic going from A to D. B would prefer to hand that traffic over to C on the West Coast (so that C would have to absorb the cost of carrying the traffic cross-country), while C would prefer to get the traffic via its East Coast peering point with B (so that B would have carried the traffic across the country). What BGP mechanism might C use, so that B would hand over A-to-D traffic at its East Coast peering point? To answer this question, you will need to dig into the BGP specification.

One way for C to force B to hand over all of B’s traffic to D on the east coast is for C to only advertise its route to D via its east coast peering point with C.



## P20

> Suppose ASs X and Z are not directly connected but instead are connected by AS Y. Further suppose that X has a peering agreement with Y, and that Y has a peering agreement with Z. Finally, suppose that Z wants to transit all of Y’s traffic but does not want to transit X’s traffic. Does BGP allow Z to implement this policy?

Yes, BGP allows Z to implement the given policy.

Given data:

The network contains Autonomous Systems AS X, AS Y and AS Z.

*BGP* means  *Border Gateway Protocol*.  It is an Inter-AS routing protocol.

- It takes the subnet reachability data from neighboring AS.
- AS X has an agreement of peering with AS Y.
- AS Y has an agreement of peering with AS Z.
- This protocol permits AS Z to develop the policy.
- The *BGP* route trailers are held by each AS.
- AS Y should present AS X that, it has no path to Z.
- The system AS X is ignorant that AS Y has path to AS Z.
- AS X never forward the traffic.
- AS Z can transfer all of Y’s traffic.

## P22

> In Section 5.7, we saw that it was preferable to transport SNMP messages in unreliable UDP datagrams. Why do you think the designers of SNMP chose UDP rather than TCP as the transport protocol of choice for SNMP?

Using UDP to transmit packets can reduce network overhead and meet the requirements, which is in line with the guiding ideology of SNMP as simple as possible
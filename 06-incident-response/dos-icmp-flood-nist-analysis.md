# DoS ICMP Flood Incident Analysis (NIST CSF)

## Security Event Summary

The organization experienced a Denial-of-Service (DoS) attack that disrupted internal network services for approximately two hours. During the attack, a large volume of ICMP packets flooded the network, overwhelming system resources and preventing normal internal traffic from accessing network resources.

The root cause of the incident was an unconfigured firewall that allowed unrestricted ICMP traffic into the network. A malicious actor exploited this vulnerability to overwhelm the internal network.

The incident response team mitigated the attack by blocking incoming ICMP packets, taking non-critical services offline, and restoring critical network services.

---

## Identify

### Type of Attack
- Denial-of-Service (DoS) attack using an ICMP flood

### Systems Impacted
- Internal network infrastructure
- Network services and resources
- Firewall configuration

### Root Cause
- Unconfigured firewall
- Lack of ICMP traffic filtering and rate limiting

---

## Protect

To better protect the organization from future incidents, the following actions should be implemented:

- Configure firewall rules to limit incoming ICMP traffic
- Apply rate limiting for ICMP requests
- Conduct regular firewall and network configuration audits
- Segment critical systems from non-critical systems
- Strengthen internal security policies and procedures

These measures will reduce the likelihood of another DoS attack affecting the internal network.

---

## Detect

To improve detection of future incidents, the organization should:

- Deploy network monitoring tools to identify abnormal traffic spikes
- Configure alerts for unusual ICMP traffic volume
- Use an Intrusion Detection System (IDS) or Intrusion Prevention System (IPS)
- Continuously review logs from firewalls and monitoring systems

These methods will improve visibility into suspicious traffic and support faster detection.

---

## Respond

For future incidents, the organization should follow a structured response plan:

- Block malicious or suspicious traffic immediately
- Isolate affected network segments if necessary
- Prioritize restoration of critical services
- Collect and analyze logs to identify indicators of attack
- Notify internal stakeholders and document all response actions

A documented response process will help reduce downtime and improve coordination.

---

## Recover

To recover effectively from similar incidents in the future, the organization should:

- Restore critical services first
- Validate that systems are functioning normally before reconnecting non-critical services
- Review and update firewall configurations
- Document lessons learned from the incident
- Update the incident response plan based on findings

These recovery steps will support business continuity and improve preparedness for future attacks.

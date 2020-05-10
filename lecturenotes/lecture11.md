## Firewalls
Firewall l is a system, or group of systems, that enforces an access control policy between networks. Click Play in the figure to view a firewall.
### Properties
- Firewalls are resistant to network attacks.
- Firewalls are the only transit point between internal corporate networks and external networks because all traffic flows through the firewall.
- Firewalls enforce the access control policy.
### Benefits
- They prevent the exposure of sensitive hosts, resources, and applications to untrusted users.
- They sanitize protocol flow, which prevents the exploitation of protocol flaws.
- They block malicious data from servers and clients.
- They reduce security management complexity by off-loading most of the network access control to a few firewalls in the network.
### Limitations
- A misconfigured firewall can have serious consequences for the network, such as becoming a single point of failure.
- The data from many applications cannot be passed over firewalls securely.
- Users might proactively search for ways around the firewall to receive blocked material, which exposes the network to potential attack.
- Network performance can slow down.
- Unauthorized traffic can be tunneled or hidden as legitimate traffic through the firewall.

### Packet filtering (stateless) firewall
Filter packet content Layer3(Network layer) and Layer4 (Transport Layer). It is part of router firewall

### Statefull firewall
A stateful inspection firewall allows or blocks traffic based on state, port, and protocol. It monitors all activity from the opening of a connection until it is closed. Filtering decisions are made based on both administrator-defined rules as well as context, which refers to using information from previous connections and packets belonging to the same connection

### Application gateway firewall (proxy firewall)
ilters information at Layers 3, 4, 5, and 7 of the OSI reference model. Most of the firewall control and filtering is done in software. When a client needs to access a remote server, it connects to a proxy server. The proxy server connects to the remote server on behalf of the client. Therefore, the server only sees a connection from the proxy server 

### Other firewall methods
- Host-based (server and personal) firewall - A PC or server with firewall software running on it.
- Transparent firewall - Filters IP traffic between a pair of bridged interfaces.
- Hybrid firewall - A combination of the various firewall types. For example, an application inspection firewall combines a stateful firewall with an application gateway firewall

### Next gen firewall
- Standard firewall capabilities like stateful inspection
- Integrated intrusion prevention
- Application awareness and control to see and block risky apps
- Upgrade paths to include future information feeds
- Techniques to address evolving security threats

## Honeypot
сами знаете

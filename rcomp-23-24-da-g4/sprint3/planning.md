# PLANEAMENTO

## BACKLOG

| TASK  | DESCRIPTION                                                                                                                                                                                                                                                | ASSIGNED STUDENT NAME | STUDENT NUMBER |
|-------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|----------------|
| T.3.1 | Update the building1.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 1.                                                                                                   | Marcelo Ramos         | 1221638        |
| T.3.2 | Update the building2.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 2.Final integration of each member’s Packet Tracer simulation into a single simulation (campus.pkt). | Tiago Correia         | 1211742        |
| T.3.3 | Update the building3.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 3                                                                                                    | Dephane Cabral        | 1221636        |
| T.3.3 | Update the building4.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 4.                                                                                                   | Rafael Rocha          | 1201260        |

---
**Versão do CISCO PACKET TRACER** - 8.2.1.188

**Modelo de switch usado** - Switch-PT-Empty

**Modelo de VoIP phones** - 7960 model

**Modelo de Router** -  2811 model

**Endereço IPv4 do router ISP** - 5.60.37.18/30

---
## OSFP AREA IDS

Cada edifício terá a sua própria área OSPF, nomeada por um id unico.

A distribuição dos ids para cada edificio é a seguinte:

| Building  | OSPF ID  |
|-----------|----------|
| backbone  | 0        |
| 1         | 1        |
| 2         | 2        |
| 3         | 3        |
| 4         | 4        |

---

## HTTP Servers

In addition to the already existing server, a new server must be added to the local DMZ network in each building. Each new server will have a manually set IPv4 address. The HTTP/HTTPS service will be enabled on these servers, and a simple HTML page should be created, identifying the building it belongs to.

| Building  | New Server IPv4 Address |
|-----------|-------------------------|
| 1         | 172.21.56.131           |
| 2         | 172.21.60.131           |
| 3         | 172.21.60.195           |
| 4         | 172.21.61.3             |

These IPv4 addresses should be manually assigned to each new HTTP server in the corresponding building's DMZ network.

---

## DHCPv4 Service

The router in each building must provide the DHCPv4 service to all IPv4 networks within the building, except for DMZ networks and the backbone where IPv4 node addresses are static and manually set (routers and servers).

For the VoIP VLAN, the DHCP server configuration must include option 150, representing the IP address of the TFTP (Trivial File Transfer Protocol) server to be used by Cisco IP phones model 7960 to download the phone’s configuration file.

---

## VoIP Service

Each building's router handles VoIP services for the local network. IP phones (Cisco 7960 model) should be connected for local testing. Switch ports for these phones must enable voice VLAN and disable access VLAN.

Incoming calls destined for another building's prefix are forwarded to that building's router.

The following table shows the phone numbers assigned to each building:

| Building  | Phone Numbers |
|-----------|---------------|
| 1         | 1001 , 1002   |
| 2         | 2001 , 2002   |
| 3         | 3001 , 3002   |
| 4         | 4001 , 4002   |

---

## DNS Setup

One DNS domain will be established in each building. The team member overseeing building 1 will create the DNS domain matching the team’s repository name (rcomp-23-24-cc-gn), serving as the highest-level domain, akin to the DNS root domain. Other team members will create local DNS domains named as: building-X.rcomp-23-24-cc-gn, where X is the building number.

| Building  | DNS Domain                     |
|-----------|--------------------------------|
| 1         | rcomp-23-24-da-g4              |
| 2         | building-2.rcomp-23-24-da-g4   |
| 3         | building-3.rcomp-23-24-da-g4   |
| 4         | building-4.rcomp-23-24-da-g4   |


### DNS Server Configuration
In each building, a DNS name server is required to support the local DNS domain. The server added to each DMZ in the previous sprint should be used for this purpose.

| Domain Name                  | Name Server                 | IPv4 Address  |
|------------------------------|-----------------------------|---------------|
| rcomp-23-24-cc-gn            | ns.rcomp-23-24-da-g4        | 172.21.56.130 |
| building-2.rcomp-23-24-da-g4 | ns.rcomp-23-24-da-g4        | 172.21.60.130 |
| building-3.rcomp-23-24-da-g4 | ns.rcomp-23-24-da-g4        | 172.21.60.194 |
| building-4.rcomp-23-24-da-g4 | ns.rcomp-23-24-da-g4        | 172.21.61.2   |



### DNS Records:
- All HTTP servers named `server1` (A record).
- Each domain has `www` and `web` aliases pointing to `server1`.
- An additional alias `dns` mapped to the DNS server's A record.

### DNS Configuration for Clients:
- End-nodes use local DNS server.
- DHCP-configured devices: Include DNS server info and default domain name.
- Manually configured devices: Set DNS server info manually.


---

## NAT (Network Address Translation):
- Static NAT used for traffic redirection.
- HTTP and HTTPS requests on backbone interface redirected to local DMZ DNS server.
- HTTP/HTTPS service enabled on DNS server with a simple identifying HTML page.



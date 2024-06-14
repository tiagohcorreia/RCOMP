# BUILDING 1 ROUTER CONFIGURATION

## SUB-INTERFACE FastEthernet0/0.1

- **VLAN ID**: 343 (backbone)
- **IPv4 ADDRESS**: 172.21.48.3/24

## SUB-INTERFACE FastEthernet0/1.1

- **VLAN ID**: 344 (b1-f0)
- **IPv4 ADDRESS**: 172.21.60.1/26

## SUB-INTERFACE FastEthernet0/1.2

- **VLAN ID**: 345 (b1-f1)
- **IPv4 ADDRESS**: 172.21.60.65/26

## SUB-INTERFACE FastEthernet0/1.3

- **VLAN ID**: 346 (b1-wifi)
- **IPv4 ADDRESS**: 172.21.56.1/25

## SUB-INTERFACE FastEthernet0/1.4

- **VLAN ID**: 347 (b1-dmz)
- **IPv4 ADDRESS**: 172.21.56.129/25

## SUB-INTERFACE FastEthernet0/1.5

- **VLAN ID**: 348 (b1-voip)
- **IPv4 ADDRESS**: 172.21.57.1/25

## ROUTING TABLE

| NETWORK NAME | NETWORK ADDRESS      | NEXT-HOP   |
|--------------|----------------------|------------|
| b2-f0        | 172.21.57.128/25     | 5.60.37.18 |
| b2-f1        | 172.21.58.0/25       | 5.60.37.18 |
| b2-voip      | 172.21.58.128/25     | 5.60.37.18 |
| b2-wifi      | 172.21.49.0/24       | 5.60.37.18 |
| b2-dmz       | 172.21.60.128/26     | 5.60.37.18 |
| ___          | ___                  | ___        |
| b3-f0        | 172.21.59.0/25       | 5.60.37.18 |
| b3-f1        | 172.21.50.0/24       | 5.60.37.18 |
| b3-wifi      | 172.21.51.0/24       | 5.60.37.18 |
| b3-voip      | 172.21.52.0/24       | 5.60.37.18 |
| b3-dmz       | 172.21.60.192/26     | 5.60.37.18 |
| ___          | ___                  | ___        |
| b4-f0        | 172.21.59.128/25     | 5.60.37.18 |
| b4-f1        | 172.21.53.0/24       | 5.60.37.18 |
| b4-wifi      | 172.21.54.0/24       | 5.60.37.18 |
| b4-voip      | 172.21.55.0/24       | 5.60.37.18 |
| b4-dmz       | 172.21.61.0/26       | 5.60.37.18 |

---
# FLOOR 0 OUTLETS

**b1-f0-pc**: 172.21.60.2/26

---
#  FLOOR 1 OUTLETS

**b1-f1-pc**: 172.21.60.66/26

---
# DMZ

- **b1-f0-server**: 172.21.56.130/25
- **b1-f1-server**: 172.21.56.131/25


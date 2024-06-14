# BUILDING 3 ROUTER CONFIGURATION

## SUB-INTERFACE FastEthernet0/0.1

- **VLAN ID**: 354 (b3-f0)
- **IPv4 ADDRESS**: 172.21.59.0/25

## SUB-INTERFACE FastEthernet0/0.2

- **VLAN ID**: 355 (b3-f1)
- **IPv4 ADDRESS**: 172.21.50.0/24

## SUB-INTERFACE FastEthernet0/0.3

- **VLAN ID**: 356 (b3-wifi)
- **IPv4 ADDRESS**: 172.21.51.0/24
-
## SUB-INTERFACE FastEthernet0/0.4

- **VLAN ID**: 357 (b3-voip)
- **IPv4 ADDRESS**: 172.21.52.0/24

## SUB-INTERFACE FastEthernet0/0.5

- **VLAN ID**: 358 (b3-dmz)
- **IPv4 ADDRESS**: 172.21.60.192/26

## ROUTING TABLE

| NETWORK    | IPv4 NETWORK ADDRESS |
|------------|----------------------|
| backbone   | 172.21.48.0/24       |
| ___        | ___                  |
| b1-f0      | 172.21.60.0/26       |
| b1-f1      | 172.21.60.64/26      |
| b1-wifi    | 172.21.56.0/25       |
| b1-dmz     | 172.21.56.128/25     |
| b1-voip    | 172.21.57.0/25       |
| ___        | ___                  |
| b2-f0      | 172.21.57.128/25     |
| b2-f1      | 172.21.58.0/25       |
| b2-voip    | 172.21.58.128/25     |
| b2-wifi    | 172.21.49.0/24       |
| b2-dmz     | 172.21.60.128/26     |
| ___        | ___                  |
| b4-f0      | 172.21.59.128/25     |
| b4-f1      | 172.21.53.0/24       |
| b4-wifi    | 172.21.54.0/24       |
| b4-voip    | 172.21.55.0/24       |
| b4-dmz     | 172.21.61.0/26       |
---
# FLOOR 0 OUTLETS

**b3-f0-pc**: 172.21.48.0

---
#  FLOOR 1 OUTLETS

**b3-f1-pc**: 172.21.48.8

---
# DMZ

- **b3-f1-server01**: 172.21.48.6
- **b3-f0-server01**: 172.21.48.3


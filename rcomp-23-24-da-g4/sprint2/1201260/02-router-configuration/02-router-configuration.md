# ROUTER CONFIGURATION - BUILDING 4

## Router

- Foi adicionado um router 2811.
- Para ips da sub interfaces no router das varias vlans, foi usado o primeiro enderenço disponel
  (para a rede 172.21.59.128/25 foi usado o enderenço 172.21.59.129 como ip da sub interface com a lan)

---

## EDIFÍCIO 4

| NETWORK | MAXIMUM POSSIBLE NODES  | MINIMUM PREFIX-LENGTH   | NETWORK ADDRESS SPACE SIZE  |
|---------|-------------------------|-------------------------|-----------------------------|
| b4-f0   | 120                     | 25                      | 128                         |
| b4-f1   | 150                     | 24                      | 256                         |
| b4-wifi | 190                     | 24                      | 256                         |
| b4-dmz  | 40                      | 26                      | 64                          |
| b4-voip | 170                     | 24                      | 256                         |

---

## ENDEREÇOS DAS REDES

|  NETWORK  | IPv4 NETWORK ADDRESS  
|:---------:|:--------------:
| b4-f0      | 172.21.59.128/25     |
| b4-f1      | 172.21.53.0/24       |
| b4-wifi    | 172.21.54.0/24       |
| b4-voip    | 172.21.55.0/24       |
| b4-dmz     | 172.21.61.0/26       |

---
## ENDEREÇOS DOS DISPOSITIVOS DE BACKBONE

**ENDEREÇO DA REDE DO ROUTER** 

|   DISPOSITIVO    | ENDEREÇO IPv4  |
|:----------------:|:--------------:|
|    b4-router     | 172.21.48.6    |

---

## ROUTING TABLE

| NETWORK NAME | NETWORK ADDRESS      | NEXT-HOP    |
|--------------|----------------------|-------------|
| b1-f0        | 172.21.60.0/26       | 172.21.48.3 |
| b1-f1        | 172.21.60.64/26      | 172.21.48.3 |
| b1-wifi      | 172.21.56.0/25       | 172.21.48.3 |
| b1-dmz       | 172.21.56.128/25     | 172.21.48.3 |
| b1-voip      | 172.21.57.0/25       | 172.21.48.3 |
| ___          | ___                  | ___         |
| b2-f0        | 172.21.57.128/25     | 172.21.48.4 |
| b2-f1        | 172.21.58.0/25       | 172.21.48.4 |
| b2-voip      | 172.21.58.128/25     | 172.21.48.4 |
| b2-wifi      | 172.21.49.0/24       | 172.21.48.4 |
| b2-dmz       | 172.21.60.128/26     | 172.21.48.4 |
| ___          | ___                  | ___         |
| b3-f0        | 172.21.59.0/25       | 172.21.48.5 |
| b3-f1        | 172.21.50.0/24       | 172.21.48.5 |
| b3-wifi      | 172.21.51.0/24       | 172.21.48.5 |
| b3-voip      | 172.21.52.0/24       | 172.21.48.5 |
| b3-dmz       | 172.21.60.192/26     | 172.21.48.5 |


---

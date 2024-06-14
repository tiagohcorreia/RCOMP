# ROUTER CONFIGURATION - BUILDING 2

## Router

- Foi adicionado um router 2811.

---

## EDIFÍCIO 2

| NETWORK  | MAXIMUM POSSIBLE NODES  | MINIMUM PREFIX-LENGTH  | NETWORK ADDRESS SPACE SIZE  |
|:--------:|:-----------------------:|:----------------------:|:---------------------------:|
|  b2-f0   |           90            |           25           |             128             |
|  b2-f1   |           120           |           25           |             128             |
| b2-wifi  |           220           |           24           |             256             |
|  b2-dmz  |           50            |           26           |             64              |
| b2-voip  |           110           |           25           |             128             |

---

## ENDEREÇOS DAS REDES

|  NETWORK  | PREFIX-LENGTH  | IPv4 NETWORK ADDRESS  | NEXT AVAILABLE ADDRESS  |
|:---------:|:--------------:|:---------------------:|:-----------------------:|
| backbone  |       24       |    172.21.48.0/24     |       172.21.49.0       |
|  b2-wifi  |       24       |    172.21.49.0/24     |       172.21.50.0       |
|   b2-f0   |       25       |   172.21.57.128/25    |       172.21.58.0       |
|   b2-f1   |       25       |    172.21.58.0/25     |      172.21.58.128      |
|  b2-voip  |       25       |   172.21.58.128/25    |       172.21.59.0       |
|  b2-dmz   |       26       |   172.21.60.128/26    |      172.21.60.192      |

---
## ENDEREÇOS DOS DISPOSITIVOS DE BACKBONE

**ENDEREÇO DA REDE DE BACKBONE** 172.21.48.0/24

|    DISPOSITIVO    | ENDEREÇO IPv4  |
|:-----------------:|:--------------:|
|     b2-router     |  172.21.48.4   |
| b2-switch01 (IC)  |  172.21.48.8   |

---

## Imagem

![ROUTER CONFIGURATION](/imagens/router-configuration.png)

---
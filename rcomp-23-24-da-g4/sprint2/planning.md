# PLANEAMENTO

## BACKLOG

| TASK  | DESCRIPTION                                                                                                                                                                                            | ASSIGNED STUDENT NAME | STUDENT NUMBER |
|-------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|----------------|
| T.2.1 | Development of a layer two and layer three Packet Tracer simulation for building 1, encompassing the campus backbone. Integration of every member’s Packet Tracer simulation into a single simulation. | Marcelo Ramos         | 1221638        |
| T.2.2 | Development of a layer two and layer three Packet Tracer simulation for building 2, encompassing the campus backbone.                                                                                  | Tiago Correia         | 1211742        |
| T.2.3 | Development of a layer two and layer three Packet Tracer simulation for building 3, encompassing the campus backbone.                                                                                  | Dephane Cabral        | 1221636        |
| T.2.3 | Development of a layer two and layer three Packet Tracer simulation for building 4, encompassing the campus backbone.                                                                                  | Rafael Rocha          | 1201260        |

---
**Versão do CISCO PACKET TRACER** - 8.2.1.188

**Modelo de switch para ser usado** - Switch-PT-Empty

**Modelo de VoIP phones** - 7960 model

**Modelo de Router** -  2811 model

**ID da VLAN padrão** - 1

**VTP Domain** - r2324dag4

**Bloco de endereços IPv4 disponíveis** - 172.21.48.0/20

**Endereço IPv4 do router ISP** - 5.60.37.18/30

---
## NOMEAÇÃO DE DISPOSITIVOS

A nomeação dos dispositivos no PACKET TRACER deve seguir o seguinte estilo: **b[number-of-building] - f[number-of-floor] - [type-of-device][device-count]** (os espaços são para serem ignorados; só foram introduzidos para facilitar a compreensão do leitor).

Os tipos de dispositivos estão listados a seguir com os respetivos identificadores:

| Dispositivo    | Identificador |
|----------------|---------------|
| SWITCH         | switch        |
| ROUTER         | router        |
| WORKSTATION/PC | pc            |
| ACCESS-POINT   | accesspoint   |
| IP PHONE       | phone         |
| SERVER         | server        |
| LAPTOP         | laptop        |
| DSL MODEM      | dslmodem      |

Ou seja, para dois access-points localizados no edifício 1, no piso 0, estes seriam representados da seguinte forma:

- Access-point A: **b1-f0-accesspoint01**
- Access-point B: **b1-f0-accesspoint02**

Já para os consolidation points seriam desta forma:

- Consolidation point: **b1-f0-cp2**

Para os switches que representam cross-connects pode-se também acrescentar o tipo de cross-connect que representam, por exemplo, para o edifício 1 teríamos:

- MC: **b1-mc-switch**
- IC: **b1-ic-switch**
- HC piso 0: **b1-f0-hc-switch**
- HC piso 1: **b1-f1-hc-switch**

Em relação a este método, há simplificações que podem ser feitas, por exemplo, no caso de routers e switches que representam ICs não é preciso indicar o número do piso e nem o device count porque esses dispositivos são únicos para cada edifício, portanto, basta indicar o número do edíficio e o tipo de dispositivo.

---
## VLAN's

**INTERVALO DE VLAN-ID's DISPONÍVEIS** - 343 – 364

- **b[number-building]** - indica o número do edifício. Por exemplo, "b1" significa "building 1"
- **f[number-floor]** - indica o número do piso
- **wifi** - indica a VLAN usada pelos access-points para providenciar cobertura sem-fio
- **dmz** - indica a VLAN usada pela demilitarized zone (servidores, workstation, dispositivos de infra-estrutura...)
- **voip** - indica a VLAN usada para VoIP (Voice Over Internet Protocol).

| NOME DA VLAN | VLAN-ID |
|--------------|---------|
| backbone     | 343     |
| ---          | ---     |
| b1-f0        | 344     |
| b1-f1        | 345     |
| b1-wifi      | 346     |
| b1-dmz       | 347     |
| b1-voip      | 348     |
| ---          | ---     |
| b2-f0        | 349     |
| b2-f1        | 350     |
| b2-wifi      | 351     |
| b2-dmz       | 352     |
| b2-voip      | 353     |
| ---          | ---     |
| b3-f0        | 354     |
| b3-f1        | 355     |
| b3-wifi      | 356     |
| b3-dmz       | 357     |
| b3-voip      | 358     |
| ---          | ---     |
| b4-f0        | 359     |
| b4-f1        | 360     |
| b4-wifi      | 361     |
| b4-dmz       | 362     |
| b4-voip      | 363     |

---
## NETWORKS

Haverá uma network para cada VLAN.

**Bloco de endereços IPv4 disponíveis** - 172.21.48
.0/20 (permite um total de 4096 nodes, sendo que precisamos dum bloco de endereços com capacidade para no mínimo 3392 nodes)

A quantidade máxima de nodes necessários para cada VLAN está especificada a seguir:

> **OBS**: Em cada network, o primeiro e o último endereço são reservados, portanto, em cada network é necessário adicionar mais 2 endereços para além dos necessários para representar o número máximo de dispositivos. Os números nas tabelas a seguir representam a quantidade máxima de dispositivos que poderão haver, sem contar esses 2 endereços adicionais.

### BACKBONE

| MAXIMUM POSSIBLE NODES | MINIMUM PREFIX-LENGTH | NETWORK ADDRESS SPACE SIZE |
|------------------------|-----------------------|----------------------------|
| 200                    | 24                    | 256                        |

### EDIFÍCIO 1

| NETWORK    | MAXIMUM POSSIBLE NODES | MINIMUM PREFIX-LENGTH | NETWORK ADDRESS SPACE SIZE |
|------------|------------------------|-----------------------|----------------------------|
| b1-f0      | 50                     | 26                    | 64                         |
| b1-f1      | 50                     | 26                    | 64                         |
| b1-wifi    | 80                     | 25                    | 128                        |
| b1-dmz     | 100                    | 25                    | 128                        |
| b1-voip    | 67                     | 25                    | 128                        |

### EDIFÍCIO 2

| NETWORK | MAXIMUM POSSIBLE NODES | MINIMUM PREFIX-LENGTH | NETWORK ADDRESS SPACE SIZE |
|---------|------------------------|-----------------------|----------------------------|
| b2-f0   | 90                     | 25                    | 128                        |
| b2-f1   | 120                    | 25                    | 128                        |
| b2-wifi | 220                    | 24                    | 256                        |
| b2-dmz  | 50                     | 26                    | 64                         |
| b2-voip | 110                    | 25                    | 128                        |

### EDIFÍCIO 3

| NETWORK | MAXIMUM POSSIBLE NODES  | MINIMUM PREFIX-LENGTH | NETWORK ADDRESS SPACE SIZE  |
|---------|-------------------------|-----------------------|-----------------------------|
| b3-f0   | 110                     | 25                    | 128                         |
| b3-f1   | 130                     | 24                    | 256                         |
| b3-wifi | 200                     | 24                    | 256                         |
| b3-dmz  | 45                      | 26                    | 64                          |
| b3-voip | 180                     | 24                    | 256                         |

### EDIFÍCIO 4

| NETWORK | MAXIMUM POSSIBLE NODES  | MINIMUM PREFIX-LENGTH   | NETWORK ADDRESS SPACE SIZE  |
|---------|-------------------------|-------------------------|-----------------------------|
| b4-f0   | 120                     | 25                      | 128                         |
| b4-f1   | 150                     | 24                      | 256                         |
| b4-wifi | 190                     | 24                      | 256                         |
| b4-dmz  | 40                      | 26                      | 64                          |
| b4-voip | 170                     | 24                      | 256                         |


### ENDEREÇOS DAS REDES

| NETWORK      | PREFIX-LENGTH | IPv4 NETWORK ADDRESS | NEXT AVAILABLE ADDRESS |
|--------------|---------------|----------------------|------------------------|
| backbone     | 24            | 172.21.48.0/24       | 172.21.49.0            |
| ___          | ___           | ___                  | ___                    |
| b2-wifi      | 24            | 172.21.49.0/24       | 172.21.50.0            |
| b3-f1        | 24            | 172.21.50.0/24       | 172.21.51.0            |
| b3-wifi      | 24            | 172.21.51.0/24       | 172.21.52.0            |
| b3-voip      | 24            | 172.21.52.0/24       | 172.21.53.0            |
| b4-f1        | 24            | 172.21.53.0/24       | 172.21.54.0            |
| b4-wifi      | 24            | 172.21.54.0/24       | 172.21.55.0            |
| b4-voip      | 24            | 172.21.55.0/24       | 172.21.56.0            |
| ___          | ___           | ___                  | ___                    |
| b1-wifi      | 25            | 172.21.56.0/25       | 172.21.56.128          |
| b1-dmz       | 25            | 172.21.56.128/25     | 172.21.57.0            |
| b1-voip      | 25            | 172.21.57.0/25       | 172.21.57.128          |
| b2-f0        | 25            | 172.21.57.128/25     | 172.21.58.0            |
| b2-f1        | 25            | 172.21.58.0/25       | 172.21.58.128          |
| b2-voip      | 25            | 172.21.58.128/25     | 172.21.59.0            |
| b3-f0        | 25            | 172.21.59.0/25       | 172.21.59.128          |
| b4-f0        | 25            | 172.21.59.128/25     | 172.21.60.0            |
| ___          | ___           | ___                  | ___                    |
| b1-f0        | 26            | 172.21.60.0/26       | 172.21.60.64           |
| b1-f1        | 26            | 172.21.60.64/26      | 172.21.60.128          |
| b2-dmz       | 26            | 172.21.60.128/26     | 172.21.60.192          |
| b3-dmz       | 26            | 172.21.60.192/26     | 172.21.61.0            |
| b4-dmz       | 26            | 172.21.61.0/26       | 172.21.61.64           |


#### TABELA DE ENDEREÇOS SIMPLIFICADA

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
| b3-f0      | 172.21.59.0/25       |
| b3-f1      | 172.21.50.0/24       |
| b3-wifi    | 172.21.51.0/24       |
| b3-voip    | 172.21.52.0/24       |
| b3-dmz     | 172.21.60.192/26     |
| ___        | ___                  |
| b4-f0      | 172.21.59.128/25     |
| b4-f1      | 172.21.53.0/24       |
| b4-wifi    | 172.21.54.0/24       |
| b4-voip    | 172.21.55.0/24       |
| b4-dmz     | 172.21.61.0/26       |

## ENDEREÇOS DOS DISPOSITIVOS DE BACKBONE

**ENDEREÇO DA REDE DE BACKBONE** - 172.21.48.0/24

| DISPOSITIVO      | ENDEREÇO IPv4  |
|------------------|----------------|
| b1-router        | 172.21.48.3    |
| b2-router        | 172.21.48.4    |
| b3-router        | 172.21.48.5    |
| b4-router        | 172.21.48.6    |

255.255.255.252
## ROUTING TABLE DO ROUTER ISP

| NETWORK NAME | NETWORK ADDRESS      | NEXT-HOP    |
|--------------|----------------------|-------------|
| b1-f0        | 172.21.60.0/26       | 172.21.48.3 |
| b1-f1        | 172.21.60.64/26      | 172.21.48.3 |
| b1-wifi      | 172.21.56.0/25       | 172.21.48.3 |
| b1-dmz       | 172.21.56.128/25     | 172.21.48.3 |vlan
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
| ___          | ___                  | ___         |
| b4-f0        | 172.21.59.128/25     | 172.21.48.6 |
| b4-f1        | 172.21.53.0/24       | 172.21.48.6 |
| b4-wifi      | 172.21.54.0/24       | 172.21.48.6 |
| b4-voip      | 172.21.55.0/24       | 172.21.48.6 |
| b4-dmz       | 172.21.61.0/26       | 172.21.48.6 |
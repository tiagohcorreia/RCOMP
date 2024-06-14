# SWITCH CONFIGURATION - BUILDING 2

---
## 1. **Configuração da layer 2**

    
- Foi adicionado um switch para a building 2 
- Adicionalmente foi adicionado 2 switches dos HC
- As ligações enter os switches é representado em fibra
   
---
## 2. **Configuração de VLAN**

   - Foi defenido as seguintes VLANs em cada switch, de acordo com a distribuição no planeamento:
   
        - VLAN para floor 0.
        - VLAN para floor 1.
        - VLAN para a rede Wi-Fi.
        - VLAN para o DMZ do edifício.
        - VLAN para VoIP.
        - VLAN para o backbone do campus

      | NOME DA VLAN | VLAN-ID |
      | --- | -- |
      | b2-f0 | 349 |
      | b2-f1 | 350 |
      | b2-wifi | 351 |
      | b2-dmz | 352 |
      | b2-voip | 353 |
     
---

    
## 3. Configuração de todas as portas dos switch para modo trunk para conexões entre switches.
    
### b2-f0-swhitch01 > CLI
            
- Entrar no modo de configuração

            ```
            enable
            configure terminal
            ```

- Configurar cada port no mode trunk

            ```
            interface FastEthernet0/1
            switchport mode trunk
            interface FastEthernet1/1
            switchport mode trunk
            interface Ethernet2/1
            switchport mode trunk
            ```

 - Guardar as alterações

            ```
            end
            write memory
            ```

 ### b2-f0-swhitch02/ b2-f1-swhitch03 > CLI

            ```
            enable
            configure terminal
            interface FastEthernet0/1
            switchport mode trunk
            interface FastEthernet1/1
            switchport mode trunk
            end
            write memory
            ```
    ---


## 4. **VLAN Trunking Protocol (VTP)**

            ```
            enable
            configure terminal
            vtp domain r2324dag4
            end
            write memory  
            ```
  ---  

## 5. Configurar pelo menos um switch no modo servidor
    
- switch: b2-f0-switch01

             ```
            enable
            configure terminal
            vtp mode server
            end
            write memory
            ```
  
---
## 6. Configurar outros switches no modo cliente para receber atualizações da base de dados VLAN.

- switch: b2-f0-hc-swicth02 / b2-f1-hc-swicth03

             ```
            enable
            configure terminal
            vtp mode client
            end
            write memory
            ```

---

## 7. Imagem

![SWITCH-CONFIGURATION](/png/switch-configuration.png)

---
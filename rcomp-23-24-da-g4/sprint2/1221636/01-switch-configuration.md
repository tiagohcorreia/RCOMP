# SWITCH CONFIGURATION - BUILDING 3

---
## 1. **Configuração da layer 2**

    
- Foram adicionados 4 switch para a building 3: 1 IC, 2 HC e um consolidation point
- As ligações entre os switches são representados em fibra
   
---
## 2. **Configuração de VLAN**

   -De acordo com a distribuição no planeamento, foram definidos as seguintes VLANs em cada switch, :
   
        - VLAN para floor 0.
        - VLAN para floor 1.
        - VLAN para a rede Wi-Fi.
        - VLAN para o DMZ do edifício.
        - VLAN para VoIP.
        - VLAN para o backbone do campus

| NOME DA VLAN | VLAN-ID |
      |--------------|---------|
| b3-f0        | 354     |
| b3-f1        | 355     |
| b3-wifi      | 356     |
| b3-dmz       | 357     |
| b3-voip      | 358     |
     
---
---

    
## 3. Configuração de todas as portas dos switch para o modo trunk para as conexões entre switches.
    
### b3-f0-switch01 > CLI
            
- Entrar no modo de configuração

            ```
            enable
            configure terminal
            ```


 - Guardar as alterações

            ```
            end
            write memory
            ```


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
    
- switch: b3-f0-switch01-IC

             ```
            enable
            configure terminal
            vtp mode server
            end
            write memory
            ```
  
---
## 6. Configurar outros switches no modo cliente para receber atualizações da base de dados VLAN.

- switch: b3-f0-hc-switch1 / b3-f1-hc-switch1 /b3-f1-hc-cp-switch1

             ```
            enable
            configure terminal
            vtp mode client
            end
            write memory
            ```

---

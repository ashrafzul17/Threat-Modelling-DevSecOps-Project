# Summary MITRE ATT&CK Sequence

## Attack Description
In this scenario, an insider with authorized access to Solaris Care Connect 360 identifies, accesses, and exfiltrates proprietary quant algorithms. The insider leverages their permissions to bypass security controls, modifies logging mechanisms to avoid detection, and transfers sensitive data to external storage.

## Methodology
The attack sequence below utilizes the MITRE ATT&CK framework along with commonly employed insider threat techniques.

```mermaid
flowchart TD

    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Initial_Access fill:#F5B041,stroke:#000,stroke-width:2px
    style Defense_Evasion fill:#EB984E,stroke:#000,stroke-width:2px
    style Collection fill:#E59866,stroke:#000,stroke-width:2px
    style Exfiltration fill:#DC7633,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Insider identifies quant algorithm locations| Initial_Access[Initial Access]
    Initial_Access[Initial Access] -->|Accesses database containing algorithms| Defense_Evasion[Defense Evasion]
    Defense_Evasion[Defense Evasion] -->|Disables or manipulates logging| Collection[Collection]
    Collection[Collection] -->|Copies quant algorithms to unauthorized storage| Exfiltration[Exfiltration]
    Exfiltration[Exfiltration] -->|Transfers data to external source| Exfiltration

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
        style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
        Reconnaissance -->|T1069 - Permission Groups Discovery| MITRE
        Initial_Access -->|T1078 - Valid Accounts| MITRE
        Defense_Evasion -->|T1070 - Indicator Removal on Host| MITRE
        Collection -->|T1005 - Data from Local System| MITRE
        Exfiltration -->|T1041 - Exfiltration Over C2 Channel| MITRE
    end

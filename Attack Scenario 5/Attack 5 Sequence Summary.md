# Summary MITRE ATT&CK Sequence

## Attack Description
The attacker targets Solaris Care Connect 360 by exploiting vulnerabilities within a third-party software provider. The attacker injects malicious code into the third-party provider's software update, which is then integrated into the Solaris Care Connect 360 application. This backdoor grants the attacker persistent access to sensitive data without directly interacting with the application’s front-end defenses.

## Methodology
The attack sequence below utilizes the MITRE ATT&CK framework along with commonly used techniques.

```mermaid

flowchart TD

    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Identify third-party vendor vulnerabilities| Weaponization[Weaponization]
    Weaponization[Weaponization] -->|Insert malicious code into third-party update| Delivery[Delivery]
    Delivery[Delivery] -->|Third-party software is updated| Exploitation[Exploitation]
    Exploitation[Exploitation] -->|Compromised code installed within the application| Installation[Installation]
    Installation[Installation] -->|Attacker establishes backdoor access| Command_Control[Command and Control]
    Command_Control[Command and Control] -->|Attacker communicates through backdoor| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Exfiltrate sensitive data| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Maintain persistent access| Actions_Objectives[Actions on Objectives]

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    Reconnaissance -->|T1591 - Gather Victim Network Information| MITRE
    Weaponization -->|T1071.001 - Application Layer Protocol| MITRE
    Delivery -->|T1195.002 - Supply Chain Compromise| MITRE
    Exploitation -->|T1190 - Exploit Public-Facing Application| MITRE
    Installation -->|T1106 - Execution through API| MITRE
    Command_Control -->|T1102 - Web Service| MITRE
    Actions_Objectives -->|T1574 - Hijack Execution Flow| MITRE
    Actions_Objectives -->|T1565.001 - Data Manipulation| MITRE
    end

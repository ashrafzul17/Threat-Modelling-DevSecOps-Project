# Summary MITRE ATT&CK Sequence

## Attack Description
The attacker leverages a SQL injection vulnerability within the Solari Health 360 application to gain unauthorized access. By injecting malicious SQL code through input fields, the attacker is able to bypass authentication controls and retrieve sensitive data from the database.

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

    Reconnaissance[Reconnaissance] -->|Identifies vulnerable input fields in Solari Health 360 application| Weaponization[Weaponization]
    Weaponization[Weaponization] -->|Crafts malicious SQL payload| Delivery[Delivery]
    Delivery[Delivery] -->|Injects payload into vulnerable field| Exploitation[Exploitation]
    Exploitation[Exploitation] -->|Executes SQL code to bypass authentication| Installation[Installation]
    Installation[Installation] -->|Establishes unauthorized access| Command_Control[Command and Control]
    Command_Control[Command and Control] -->|Backdoor created for future access| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Extracts sensitive health data| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Potentially alters database information| Actions_Objectives[Actions on Objectives]

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    Reconnaissance -->|T1592 - Gather Data from Online Sources| MITRE
    Delivery -->|T1190 - Exploit Public-Facing Application| MITRE
    Exploitation -->|T1059.005 - SQL Injection| MITRE
    Installation -->|T1078 - Valid Accounts| MITRE
    Command_Control -->|T1105 - Ingress Tool Transfer| MITRE
    Actions_Objectives -->|T1003 - Data Extraction| MITRE
    Actions_Objectives -->|T1499 - Data Destruction or Manipulation| MITRE
    end

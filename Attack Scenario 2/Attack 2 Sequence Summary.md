 # Summary MITRE ATT&CK Sequence

## Attack Description
The attacker conducts detailed reconnaissance on the data lake and automated processes within the Solari Health 360 application. Using advanced techniques, they identify insecure API endpoints and flaws in process automation, enabling them to bypass security controls and access sensitive data stored in the data lake.

## Methodology
The attack sequence below utilizes the MITRE ATT&CK framework along with common techniques tailored to exploit machine processes and data vulnerabilities.

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

    Reconnaissance[Reconnaissance] -->|Identify weak API endpoints and automation flaws| Weaponization[Weaponization]
    Weaponization[Weaponization] -->|Create scripts to exploit process vulnerabilities| Delivery[Delivery]
    Delivery[Delivery] -->|Inject scripts via API or automation process| Exploitation[Exploitation]
    Exploitation[Exploitation] -->|Gain unauthorized access to data lake| Installation[Installation]
    Installation[Installation] -->|Install persistence scripts for ongoing access| Command_Control[Command and Control]
    Command_Control[Command and Control] -->|Establish communication with C&C server| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Extract or manipulate sensitive data| Actions_Objectives[Actions on Objectives]

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
        style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

        Reconnaissance -->|T1592 - Gather Victim Host Information| MITRE
        Delivery -->|T1071.001 - Application Layer Protocol: Web| MITRE
        Exploitation -->|T1190 - Exploit Public-Facing Application| MITRE
        Installation -->|T1059.003 - Command and Scripting Interpreter| MITRE
        Command_Control -->|T1095 - Standard Non-Application Layer Protocol| MITRE
        Actions_Objectives -->|T1565 - Data Manipulation| MITRE
        Actions_Objectives -->|T1003 - Data from Information Repositories| MITRE
    end

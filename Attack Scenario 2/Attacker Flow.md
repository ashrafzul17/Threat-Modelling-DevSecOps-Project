# Attacker Flow: Scenario 2

```mermaid

sequenceDiagram

    participant Attacker
    participant DataLake
    participant CnCServer
    participant BackendServer
    participant AutomatedProcess

    activate Attacker
    Attacker->>DataLake: Identify data lake and automated processes
    DataLake->>Attacker: Access points identified
    deactivate Attacker

    activate Attacker
    Attacker->>DataLake: Develop scripts targeting process vulnerabilities
    DataLake->>Attacker: Exploitable process weaknesses identified
    deactivate Attacker

    activate Attacker
    Attacker->>AutomatedProcess: Inject malicious scripts via API endpoint
    AutomatedProcess->>BackendServer: Script executed, unauthorized access gained
    deactivate Attacker

    activate BackendServer
    BackendServer->>CnCServer: Establish command and control link
    CnCServer->>BackendServer: Send commands to extract or alter data
    BackendServer->>CnCServer: Data extracted/altered
    deactivate BackendServer


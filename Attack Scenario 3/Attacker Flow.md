This is an Attacker Flow based on Scenario 3

```mermaid

sequenceDiagram

    participant Attacker
    participant SolariHealthApp
    participant Database
    participant BackendServer
    participant User

    activate Attacker
    Attacker->>SolariHealthApp: Identify vulnerable input fields (e.g., search or login forms)
    SolariHealthApp->>Attacker: Input fields identified
    deactivate Attacker

    activate Attacker
    Attacker->>SolariHealthApp: Craft malicious SQL injection payload
    SolariHealthApp->>Attacker: Payload crafted
    deactivate Attacker

    activate Attacker
    Attacker->>SolariHealthApp: Inject SQL code into vulnerable field
    SolariHealthApp->>Database: Executes injected SQL query
    deactivate Attacker

    activate Database
    Database->>SolariHealthApp: Bypasses authentication or accesses sensitive data
    deactivate Database

    activate Attacker
    Attacker->>BackendServer: Establishes unauthorized access
    BackendServer->>Attacker: Data retrieved and commands issued
    deactivate Attacker

    activate Attacker
    Attacker->>Database: Creates backdoor for persistent access
    Database->>Attacker: Backdoor established for future attacks
    deactivate Attacker

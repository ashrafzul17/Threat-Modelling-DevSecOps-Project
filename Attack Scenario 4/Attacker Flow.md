# Attacker Flow: Scenario 4

This is an Attacker Flow based on Scenario 4:  Insider Attack Taking Quant Algorithms

```mermaid

sequenceDiagram

    participant Insider
    participant SolarisCareConnect
    participant Database
    participant ExternalStorage
    participant LoggingService

    activate Insider
    Insider->>SolarisCareConnect: Identify locations of quant algorithms
    SolarisCareConnect->>Insider: Access to sensitive resources granted
    deactivate Insider

    activate Insider
    Insider->>Database: Locate and access quant algorithm files
    Database->>Insider: Files accessed
    deactivate Insider

    activate Insider
    Insider->>LoggingService: Disable or manipulate logging to cover tracks
    LoggingService->>Insider: Logging disabled or modified
    deactivate Insider

    activate Insider
    Insider->>ExternalStorage: Copy quant algorithms to unauthorized storage
    ExternalStorage->>Insider: Data copied to personal storage
    deactivate Insider

    activate Insider
    Insider->>ExternalStorage: Exfiltrate sensitive data to external source
    ExternalStorage->>Insider: Data successfully exfiltrated
    deactivate Insider

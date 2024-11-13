# Attacker Flow: Scenario 5

This is an Attacker Flow based on Attack Scenario 5: Supply Chain Attack Compromising Third-Party Software

```mermaid

sequenceDiagram

    participant Attacker
    participant ThirdPartyProvider
    participant SolarisApp
    participant BackendServer
    participant User

    activate Attacker
    Attacker->>ThirdPartyProvider: Identify target third-party software
    ThirdPartyProvider->>Attacker: Vulnerability discovered in software
    deactivate Attacker

    activate Attacker
    Attacker->>ThirdPartyProvider: Inject malicious code into third-party software
    ThirdPartyProvider->>Attacker: Code injection successful
    deactivate Attacker

    activate ThirdPartyProvider
    ThirdPartyProvider->>SolarisApp: Release compromised software update
    SolarisApp->>BackendServer: Integrate compromised software as update
    deactivate ThirdPartyProvider

    activate BackendServer
    BackendServer->>Attacker: Malicious code executed, backdoor created
    BackendServer->>Attacker: Access granted to application infrastructure
    deactivate BackendServer

    activate Attacker
    Attacker->>SolarisApp: Exfiltrate sensitive data from application
    SolarisApp->>BackendServer: Continues regular operations unaware
    deactivate Attacker

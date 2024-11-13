# STRIDE Model

We use STRIDE to to demonstrate the current controls in place for the application.

This diagram outlines potential threats identified through STRIDE and highlights corresponding mitigation measures for each threat.

 This approach helps protect sensitive quant algorithms from unauthorized insider access and manipulation.

 ```mermaid
 graph TD

    subgraph User Interaction
        A[User] -->|Access Request| B[Internal Portal]
    end

    subgraph Internal Portal
        B -->|Access| C[Quant Algorithms Storage]
        B -->|Execute| D[Data Query Processing]
        B -->|Receive Input| E[Input Validation]
    end

    subgraph Data Storage
        C -->|Store/Fetch Algorithms| F[Database]
    end

    A((User)) -.->|Authentication| G[Authentication Mechanism]

    B -.->|Logging| H[Logging Service]

    A -.->|Access| I[Admin Panel]
    I -.->|Controls| J[Admin Functionality]

    %% Threats
    T1([Spoofing: Spoof User Identity]) -.-> A
    T2([Tampering: Alter Requests]) -.-> B
    T3([Repudiation: Deny Data Access]) -.-> H
    T4([Information Disclosure: Unauthorized Access to Algorithms]) -.-> F
    T5([Denial of Service: Overload Internal Portal]) -.-> B
    T6([Elevation of Privilege: Unauthorized Admin Access]) -.-> I

    %% Mitigations
    M1([Mitigation: Strong Authentication]) --> T1
    M2([Mitigation: Data Integrity Checks]) --> T2
    M3([Mitigation: Non-repudiation Mechanisms]) --> T3
    M4([Mitigation: Role-Based Access Control]) --> T4
    M5([Mitigation: Rate Limiting]) --> T5
    M6([Mitigation: Privileged Access Management]) --> T6

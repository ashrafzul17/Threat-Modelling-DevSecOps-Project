# STRIDE Model

We use STRIDE to demonstrate the current controls in place for the application.

This approach helps protect the Solaris Care Connect 360 application from unauthorized third-party software manipulation and access risks.

```mermaid

graph TD

    subgraph Third-Party Software Integration
        A[External Vendor] -->|Software Update| B[Third-Party Component]
        B -->|Communicate| C[Application Backend]
    end

    subgraph Application Backend
        C -->|Access| D[Internal Database]
        C -->|Execute| E[Business Logic]
        C -->|Receive Input| F[Input Validation]
    end

    subgraph Data Storage
        D -->|Store/Fetch Data| G[Database]
    end

    A((External Vendor)) -.->|Authentication| H[Authentication Mechanism]

    B -.->|Logging| I[Logging Service]

    A -.->|Access| J[Admin Interface]
    J -.->|Controls| K[Admin Functionality]

    %% Threats
    T1([Spoofing: Impersonate Vendor Identity]) -.-> A
    T2([Tampering: Modify Software Update]) -.-> B
    T3([Repudiation: Deny Update Integrity]) -.-> I
    T4([Information Disclosure: Data Leak via Compromised Component]) -.-> G
    T5([Denial of Service: Disrupt Application Backend]) -.-> C
    T6([Elevation of Privilege: Unauthorized Backend Access]) -.-> J

    %% Mitigations
    M1([Mitigation: Vendor Authentication]) --> T1
    M2([Mitigation: Digital Signatures]) --> T2
    M3([Mitigation: Integrity and Logging Checks]) --> T3
    M4([Mitigation: Data Encryption]) --> T4
    M5([Mitigation: Network Monitoring and Rate Limiting]) --> T5
    M6([Mitigation: Access Controls]) --> T6

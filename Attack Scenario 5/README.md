# Attack 5 Summary: Supply Chain Attack Compromising Third-Party Software

## Stages of the Attack

### Origins
The attack is initiated by compromising a third-party software dependency used in the Solaris Care Connect 360 application. The attacker injects malicious code into the software or library, which is then distributed through regular software updates.

### Reconnaissance
The attacker identifies a third-party software provider or open-source dependency that Solaris Care Connect 360 relies on. Research is conducted to understand how to access and compromise the supply chain component without detection.

### Weaponization
Malware is embedded into the third-party software by the attacker, with the code crafted to activate upon integration into Solaris Care Connect 360. This could include creating backdoor access, installing keyloggers, or exfiltrating sensitive data.

### Delivery
The compromised software update is released by the third-party provider, which is then integrated or updated within Solaris Care Connect 360’s infrastructure as part of normal update processes.

### Exploitation
Upon installation, the malware activates and grants the attacker unauthorized access to Solaris Care Connect 360’s systems or initiates data exfiltration, bypassing direct security controls.

### Installation
The attacker establishes persistent access by creating or exploiting backdoor channels, ensuring prolonged unauthorized entry or continued exfiltration of sensitive data from the application.

#### Actions on Objectives
With ongoing access, the attacker can extract sensitive patient data, manipulate health records, or disrupt system functions to achieve further malicious goals.

```mermaid
flowchart LR

    A[Third-Party Provider] --> B{Supply Chain Component}

    B -->|Identify component| C[Reconnaissance]

    C -->|Identify vulnerabilities| D[Weaponization]

    D -->|Embed malware| E[Delivery]

    E -->|Deploy compromised software| F[Exploitation]

    F -->|Grant unauthorized access| G[Installation]

    G -->|Establish persistence| H[Actions on Objectives]

    H -->|Extract sensitive data| I[Objectives]
    H -->|Manipulate health records| I

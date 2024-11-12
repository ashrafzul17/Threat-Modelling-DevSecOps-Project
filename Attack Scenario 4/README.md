# Attack 4 Summary: Insider Attack Taking Quant Algorithms

## Stages of the Attack

### Origins
The attack originates from a trusted insider within the organization, who has privileged access to Solaris Care Connect 360’s sensitive resources, including proprietary quant algorithms. The insider sees an opportunity to profit by exfiltrating these algorithms to an external entity.

### Reconnaissance
The insider, leveraging their access, identifies specific files and locations where quant algorithms are stored within the Solaris infrastructure. This includes locating sensitive databases, cloud storage, and documentation detailing algorithm functionality.

### Weaponization
Using their existing credentials, the insider prepares to extract and transfer the quant algorithms. They may also attempt to disable logging or other tracking features to obscure their activities.

### Delivery
The insider begins exporting quant algorithms by copying the data to unauthorized storage locations, such as external drives, email, or a personal cloud service. They utilize obfuscation techniques to evade detection.

### Exploitation
The insider misuses their access privileges, bypassing any established access control policies to gain unrestricted access to the algorithms and associated documentation. They may escalate permissions within the system to enable unrestricted data transfers.

### Installation
If necessary, the insider installs backdoors or alternate access mechanisms to ensure continued, stealthy access to Solaris’s infrastructure, enabling them to return later without suspicion.

### Actions on Objectives
The insider successfully exfiltrates the quant algorithms and transfers them to an external party or competitor. This results in significant intellectual property theft, loss of competitive advantage, and potential reputational damage to Solaris.

```mermaid
flowchart LR

    A[Identify Sensitive Data Locations] --> B[Plan Data Extraction]
    B --> C[Disable Logging]
    C --> D[Copy Algorithms to Unauthorized Location]
    D --> E[Use Personal Storage Service]
    E --> F[Escalate Privileges if Needed]
    F --> G[Ensure Stealthy Access]
    G --> H[Exfiltrate Quant Algorithms]

    subgraph InsiderActions [Insider Actions]
        A
        B
        C
        D
        E
        F
        G
        H
    end

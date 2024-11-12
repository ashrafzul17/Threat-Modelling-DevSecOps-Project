# Attack 3 Summary: SQL Injection Attack

## Stages of the Attack

### Origins
The attack originates from a malicious actor familiar with SQL injection vulnerabilities. Recognizing the critical nature of the Solaris Care Connect 360 application and its large database of sensitive health information, the attacker identifies it as a prime target for unauthorized data extraction.

### Reconnaissance
The attacker investigates the application’s forms and query parameters, focusing on input fields and URL parameters that may directly interact with the application’s SQL database. This research helps identify potential vulnerabilities in the application's handling of user input.

### Weaponization
Malicious SQL code is crafted to exploit vulnerabilities in the application’s database queries. This code aims to manipulate SQL statements to bypass authentication or retrieve sensitive data without authorization.

### Delivery
The attacker injects the crafted SQL code into vulnerable input fields within the Solaris Care Connect 360 application, such as search fields, login forms, or query parameters in the URL. This input is designed to alter the intended SQL commands sent to the database.

### Exploitation
Once the SQL injection is successfully executed, the attacker manipulates SQL queries to bypass authentication or access unauthorized data. This may result in data extraction, modification, or deletion depending on the nature of the injected SQL commands.

### Installation
If persistent access is desired, the attacker may create a backdoor account in the database, enabling repeated access without needing to reinject the SQL code. This foothold allows further manipulation or unauthorized monitoring of the database.

### Actions on Objectives
With unauthorized access to the database, the attacker can exfiltrate sensitive health records, alter patient information, or disrupt normal application functionality. The stolen data can then be used or sold, compromising the privacy and integrity of patient information.

```mermaid

flowchart LR

    A[Reconnaissance] -->|Identify vulnerable fields| B[Weaponization]
    B -->|Craft SQL Injection code| C[Delivery]
    C -->|Inject SQL code| D[Exploitation]
    D -->|Bypass authentication| E[Installation]
    D -->|Access sensitive data| F[Actions on Objectives]
    E -->|Create backdoor access| F

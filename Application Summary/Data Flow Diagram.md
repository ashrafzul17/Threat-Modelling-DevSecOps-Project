# Data Flow Diagram

- The Data Flow Diagram is used to highlight any key critical areas of the application that will be targeted by a likely attacker.

- In the workshop, during discussion with engineering teams its important to ensure a shared understanding of potential attack vectors





```mermaid

erDiagram

    USER }|..|{ Patient : "Uses"

    CUSTOMER ||--o{ ORDER : places

    CUSTOMER ||--o{ INVOICE : "liable for"

    DELIVERY-ADDRESS ||--o{ ORDER : receives

    INVOICE ||--|{ ORDER : covers

    ORDER ||--|{ ORDER-ITEM : includes

    PRODUCT-CATEGORY ||--|{ PRODUCT : contains

    PRODUCT ||--o{ ORDER-ITEM : "ordered in"
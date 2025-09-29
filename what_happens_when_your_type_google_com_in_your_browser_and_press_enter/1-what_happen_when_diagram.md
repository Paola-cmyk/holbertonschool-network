# The skeleton of What happens when you search ```www.google.com``` and press Enter

```mermaid
flowchart TD
  A[User’s browser]
  B[DNS lookup]
  C["IP Address & Port"]
  D[TCP three‑Way handshake]
  E[Firewall check]
  F[Load-balancer]
  G[Web server]
  H[App server]
  I[Database]
  J[Responce]

  A --> B
  B --> C
  C --> D
  D --> E
  E --> F
  F --> G
  G --> H
  H --> I
  I --> J

  class B,C,D,E,F,G,H,I,J proc;
  ```



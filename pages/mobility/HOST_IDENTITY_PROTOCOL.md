# HOST IDENTITY PROTOCOL

Complete revision of the ip protocol in order to separate location and identity of a node, the protocol integrates cryptographic Host Identifiers in the ip stack, ipv4,ipv6 interoperability

```mermaid
flowchart TB
subgraph HIP
direction TB
E[V4/V6 bridge]
F[multi homing]
G[mobility]
E --> F --> G
end
subgraph IP_layer
direction TB
A[IPsec]
B[HIP]
C[Fragmentation]
D[Forward]
A --> B --> C --> D
end
B --> HIP
```
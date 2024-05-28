# Architecture



The DM3 protocol is structured in several layers. Its strictly modular architecture allows the required parts of the protocol, including libraries and APIs, to be precisely tailored to the use case.

There are 3 levels:

1. **Blockhain Layer:** This layer defines all interface APIs to other data sources (other chains, layer-2, cloud services, etc.) besides ENS (Ethereum Name Service), which is based on Ethereum.
2. **Protocol layer:** The center of the protocol is the DM3 Message Transport Protocol. Many optional and utility extensions exist on top of the core protocol.
3. **Application Layer:** The application layer includes the APIs for integration into other protocols, services, and apps and the embedded UI components for direct integration into other applications.
4. **Utility Extensions:** Modules that are useful for building user-friendly messaging applications but not directly linked to the core protocol.

??? \[image module]

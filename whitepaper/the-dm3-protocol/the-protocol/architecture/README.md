# Architecture



The DM3 protocol consists of different layers. Its strictly modular structure allows for precise tailoring of the required parts of the protocol, including the libraries and APIs, to the use case.

It consists of 3 layers:

1. **Blockhain Layer:** This layer defines all interface APIs to other data sources (other chains, layer-2, cloud services, etc.) besides ENS (Ethereum Name Service), which is based on Ethereum.
2. **Protocol layer:** Besides the core protocol (message transport protocol), many optional extensions exist.
3. **Application Layer:** The APIs for integration into other protocols, services, and apps, as well as the existing UI components for direct integration into other applications, form the Applications layer.
4. **Utility Extensions:** Modules that are useful for building user-friendly messaging applications but are not directly linked to the core protocol.

??? image module

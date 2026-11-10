# TIA Portal HMI Platform Selection

Use this as a routing aid, not as a substitute for Siemens' version/device compatibility tables. The exact feature set depends on the TIA Portal release, installed WinCC options, runtime license, target device, and firmware.

| Family | Typical target | Verify before recommending |
| --- | --- | --- |
| WinCC Basic | Basic Panels and supported basic HMI targets | Panel generation, device image/firmware, supported controls, and engineering-version compatibility |
| WinCC Comfort | Comfort Panels and supported Comfort targets | Exact panel model, runtime options, communication drivers, and feature availability in the chosen TIA release |
| WinCC Advanced | PC-based Runtime Advanced and supported panel engineering | Runtime license, Windows/runtime requirements, supported options, and target-device compatibility |
| WinCC Professional | PC-based Runtime Professional in TIA Portal | Whether the project is TIA WinCC Runtime Professional or standalone SIMATIC WinCC; server/client architecture, licenses, and supported options |
| WinCC Unified | Unified Panels and PC Runtime Unified | Unified engineering/runtime release, target device, supported web clients, JavaScript/API behavior, licenses, and migration constraints |

## Selection questions

Ask for the project version, target HMI model or PC runtime, number and type of clients, required functions, PLC/connection types, and deployment constraints. If the user only says “TIA HMI,” do not choose an edition on their behalf.

Use Siemens' official documentation and compatibility information to answer exact feature questions. In particular:

- Do not equate WinCC Unified with Comfort/Advanced just because both are engineered in TIA Portal.
- Do not equate WinCC Runtime Professional with standalone SIMATIC WinCC.
- Do not promise that a project can be upgraded or migrated without checking source and target versions, device support, and migration notes.
- Treat browser access, remote operation, scripting APIs, alarm/recipe features, redundancy, and optional packages as version- and license-dependent.

If the requested target is an older HMI family or WinCC flexible, identify it as a legacy/migration context and use its own operating and engineering documentation. Do not apply current Unified guidance to it.

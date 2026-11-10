# Source Policy and Available Manuals

## Source order

1. Inspect the user's active project, its exact TIA Portal version, target device/runtime, installed help, and supplied manuals.
2. Use the matching Siemens system manual, programming reference, communication/option manual, device operating instructions, or TIA Portal Information System/F1.
3. Use Siemens Industry Online Support and official compatibility information for current document editions and device/version support.
4. Use community material only as a lead to investigate, not as authority for version-specific or safety-relevant claims.

When a claim affects compatibility or behavior, name the document/version and relevant chapter or page when available. Clearly label unverified assumptions. Check whether a newer edition exists; do not treat a manual's publication date as proof that it is current.

## Siemens online entry points

- [Documentation for SIMATIC HMI](https://support.industry.siemens.com/cs/document/109744536): official index covering WinCC (TIA Portal) software and operator-device documentation, including Basic HMI, Unified Comfort Panels, Comfort Panels, and legacy families.
- [SIMATIC HMI Unified Comfort Panels](https://support.industry.siemens.com/cs/document/109773257): official device documentation entry; the page identifies its edition and notes when a newer edition exists.
- [Siemens compatibility tool](https://support.industry.siemens.com/cs/ww/en/view/64847781): verify supported products and compatibility rather than inferring it from similar model names.

Use the Siemens support portal to find the exact WinCC engineering manual for the user's release, especially for Unified, Basic, and Professional topics not established by the locally supplied V17 manuals. The local manuals are useful evidence for their stated release only.

## Manuals present in the user's `G:\My Drive\Manual\PLC Siemens` folder

The following inventory records file identity and applicability. It does not reproduce the manuals; do not copy the copyrighted PDFs into this repository.

| Local file | Verified identification | Use and limits |
| --- | --- | --- |
| `WCC_ProgRef_en-US.pdf` | *WinCC Engineering V17 – Programming reference*, 05/2021 | V17 programming reference. Verify target runtime before applying script/API details. |
| `WCC_Communication_en-US.pdf` | *WinCC Engineering V17 – Communication*, 05/2021 | V17 communication guidance; not evidence for every HMI family or later release. |
| `WCC_Options_en-US.pdf` | *WinCC Engineering V17 – Options*, 05/2021 | V17 option scope, including runtime-specific availability; check exact edition and license. |
| `HWComfortPanelsenUS_en-US.pdf` | *Comfort Panels*, Operating Instructions, 07/2022 | Comfort Panel device operation and commissioning; not a Unified or general engineering manual. |
| `Programming_guideline_DOC_v16.pdf` | Filename indicates a V16 programming guideline | Confirm title and scope in the PDF before citing a specific rule. |
| `S7-1200_System_Manual_A5E02486680-AL_en.pdf` | S7-1200 System Manual | Use for the target CPU only after confirming the manual revision matches CPU/firmware. |
| `HR-X Series SIEMENS S7-15001200300 SERIES Connection Guide PROFINET Communication.pdf` | HR-X Series connection guide for Siemens S7-1500/1200/300 over PROFINET | Vendor/device-specific; use only for the matching HR-X and PLC configuration. |

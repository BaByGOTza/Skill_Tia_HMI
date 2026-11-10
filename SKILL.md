---
name: tia-hmi
description: Use when a request involves Siemens HMI or WinCC in TIA Portal, including Basic, Comfort, Advanced, Professional, or Unified engineering; panel/runtime selection; screen design; tags; alarms; recipes; scripts; PLC communication; users; deployment; migration; or troubleshooting.
---

# Siemens TIA Portal HMI

Use this skill for SIMATIC HMI and WinCC work engineered in TIA Portal. Keep advice specific to the stated TIA Portal version, WinCC edition, runtime, device, and firmware. Do not treat standalone SIMATIC WinCC (SCADA) as a TIA Portal edition; handle it only when the user explicitly asks about integration or migration.

## Workflow

1. Establish the exact context: TIA Portal version/update, WinCC edition, target panel or PC runtime and firmware, connected PLC/CPU, communication path, and the requested outcome. Ask a focused question if a missing detail could change capability, compatibility, or safety.
2. Inspect the active project, existing tag/interface definitions, local instructions, and supplied manuals before proposing project-specific changes. Preserve existing naming, tag types, screen conventions, and interfaces.
3. Use [platform selection](references/platform-selection.md) to choose the relevant family and [engineering workflows](references/engineering-workflows.md) for the task. Use [source policy](references/source-policy.md) for versioned claims and citations.
4. Verify device-, edition-, and version-specific behavior against the matching Siemens manual, TIA Portal Information System/F1, or official compatibility documentation. If the exact source is unavailable, state the uncertainty and ask for the manual or project details rather than guessing.
5. Make the smallest requested change. Do not invent PLC addresses, tag names, alarm classes, security policy, screen resolution, runtime capabilities, or device limits. Derive HMI tags from the actual PLC interface or an explicitly approved mapping.
6. Validate with the checks available for the artifact: project consistency, tag/connection review, compile, simulation, and target runtime/device test. Distinguish checks actually performed from checks the user must perform in TIA Portal or on hardware.
7. Report the selected platform/version, assumptions, files or settings changed, sources used for non-obvious claims, and validation status. Reply in the user's language unless they ask otherwise.

## Engineering boundaries

- Treat Basic, Comfort, Advanced, Professional, and Unified as distinct engineering/runtime targets. Do not infer that a feature, control, script API, connection option, or migration path is shared across them.
- Separate panel device operating instructions from WinCC engineering/runtime references; a panel manual does not establish all engineering capabilities.
- For Unified, verify the specific Unified engineering version, runtime/device family, and supported browser/client behavior. Do not transpose Comfort/Advanced VBScript or C-script assumptions into Unified.
- For Professional, verify whether the question concerns WinCC Runtime Professional within TIA Portal or standalone SIMATIC WinCC. The terminology overlaps but the project and feature scope can differ.
- Keep machine/operator safety independent of HMI presentation. An HMI control is not a safety-rated function unless the complete, certified safety architecture explicitly supports that use.
- Prefer named users, least privilege, protected communications, and controlled remote access. Do not recommend exposing a panel/runtime directly to the public internet or embedding reusable credentials in project artifacts.
- Do not claim compilation, simulation, or hardware validation unless it was actually performed in the target environment.

## Reference map

- Select or distinguish an HMI family: [platform-selection.md](references/platform-selection.md)
- Design, configure, or troubleshoot HMI behavior: [engineering-workflows.md](references/engineering-workflows.md)
- Find and cite manuals without copying them: [source-policy.md](references/source-policy.md)

*** Add File: c:\Application\PLC Leaning\Skill_Tia_HMI\references\platform-selection.md
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

*** Add File: c:\Application\PLC Leaning\Skill_Tia_HMI\references\engineering-workflows.md
# HMI Engineering Workflows

These are task checklists. Confirm exact UI paths, supported properties, and runtime behavior in the matching TIA Portal version and device documentation before giving click-by-click instructions.

## Screens and navigation

- Confirm display size/orientation, operator roles, process states, and navigation requirements.
- Reuse the project's screen templates and naming conventions. Keep navigation predictable and show important state, units, and actionable alarms without relying on color alone.
- Bind controls to approved HMI tags and define behavior for unavailable, stale, invalid, and out-of-range values.
- Review touch targets, confirmation for consequential commands, and a clear way to return to a known overview screen.

## PLC tags and connections

- Identify PLC CPU, firmware, HMI target, connection type, and project-level interface.
- Trace each HMI tag to an existing PLC symbol/DB member or user-approved address mapping. Confirm data type, access direction, scaling, units, and update behavior.
- Check the configured connection endpoint, partner/interface, access permissions, and online diagnostics using the version-matched documentation.
- Never invent DB offsets, absolute addresses, connection parameters, or optimized-block access assumptions.

## Alarms

- Confirm whether alarms are discrete, analog, PLC-generated, or HMI-generated and inspect the existing alarm/tag configuration.
- Verify trigger condition, class/priority, acknowledgment behavior, text/language, timestamp source, logging, and display/archive configuration.
- Troubleshoot end to end: source condition -> PLC/HMI tag quality and value -> alarm configuration -> runtime connection -> alarm view/filter -> logging/storage -> deployment/runtime version.
- Do not confuse an alarm display with a safety function or a latched machine interlock.

## Recipes and data logging

- Confirm record structure, types/units, read/write direction, persistence, operator permissions, and behavior on partial or failed transfers.
- Check storage target/capacity, retention, time synchronization, and restart/recovery behavior against the exact runtime.
- Protect recipe import/export and logging data from unauthorized access; avoid promising durability or capacity without the relevant device/runtime specification.

## Scripts and custom behavior

- Identify the target runtime and supported scripting language/API first. Comfort/Advanced VBScript or C-script guidance does not establish Unified JavaScript/API support.
- Use documented APIs for that runtime/version, handle invalid values and communication failures, and avoid blocking or unbounded work in runtime callbacks.
- Keep scripts small and review their access to files, network resources, and user credentials. Validate in the matching simulator/runtime.

## Users, security, and remote access

- Confirm user/group model, role requirements, authentication method, password policy, certificate needs, and access paths.
- Apply least privilege, limit remote services to required networks, and use Siemens security guidance for the target device/runtime version.
- Do not hardcode passwords, recommend shared accounts, or expose HMI services directly to the public internet.

## Deployment and troubleshooting

- Verify engineering/runtime versions, device image/firmware, licensing, connection settings, and prerequisites before download or upgrade.
- Back up the project and identify whether the operation affects the live process. Do not prescribe actions that could interrupt a running machine without an explicit maintenance window and recovery plan.
- Separate engineering compile errors, transfer/download errors, runtime startup problems, PLC communication faults, and HMI behavior faults.
- Record the exact error text, affected device/runtime, project version, recent changes, and diagnostic evidence. Change one relevant variable at a time and re-test the same symptom.
- State whether validation was static review, compile, simulation, runtime test, or hardware test; do not imply one proves the others.

*** Add File: c:\Application\PLC Leaning\Skill_Tia_HMI\references\source-policy.md
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

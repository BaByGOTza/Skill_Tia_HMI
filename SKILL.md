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

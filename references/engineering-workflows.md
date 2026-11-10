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

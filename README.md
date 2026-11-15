# AI Agent Permissions and Least Privilege

## Project aim

Investigate whether least-privilege controls reduce unnecessary or unintended actions by AI agents while still allowing them to complete legitimate tasks.

## Planned experiment

Compare agents powered by models from OpenAI, Anthropic (Claude), and Google (Gemini) using one shared agent framework. Exact model versions have not yet been selected.

Each agent will receive the same tools and repeatable tasks in an isolated, four-VM Active Directory lab containing fictional company documents. A domain-joined Windows workstation will run the agents, a Windows SMB file server will enforce access, and an Ubuntu controller will coordinate trials and collect logs. A Windows domain controller will manage trial identities and groups. Tool requests and permission decisions will be recorded alongside file server audit events.

Three permission configurations are planned:

| Configuration | Access |
| --- | --- |
| Broad access | Broad access to the fictional company files within the test environment. |
| Role-based access | Access associated with a particular department or role. |
| Task-specific least privilege | Access only to the resources required for the assigned task. |

## Planned measurements

- Successful completion of legitimate tasks.
- Unnecessary file access, including access that is technically permitted.
- Attempts to perform restricted actions, recorded separately from successful access.
- Unintended modifications to files.
- Repeated-run consistency; task counts and repetition counts remain to be finalised.

## Current status

All four VMs are up and communicating in the Active Directory lab. DC01 hosts the domain, FS01 and AGENT01 are joined to it, and CTRL01 is connected to the lab network.

- **File permissions** — The Finance test account could read its assigned report and was denied access to HR.
- **Auditing** — The initial file-access auditing options were tested and worked.
- **OpenAI relay** — AGENT01 sent a request through CTRL01 using an OpenAI API key supplied on CTRL01. The test returned HTTP 200 and `OK`.

The next step is to check access to a second Finance report under the role-based and task-specific configurations, then confirm how file audit events will be collected and matched to trial logs. Comparative trials are pending.

## Project files

- [Research sources and descriptions](resources/sources/README.md)
- [Four-VM lab plan](lab-setup.md)
- [Progress log](progress-log.md)

## Planned next steps

1. Review the closest related studies and refine the research question.
2. Select and record the exact model versions and experimental settings.
3. Finish the fictional dataset and run the two-report permission check.
4. Implement controlled tools, permission checks, and action logging.
5. Pilot tasks and define expected outcomes and required permissions.
6. Run repeated comparisons across models and permission configurations.
7. Analyse security outcomes alongside task completion and document limitations.


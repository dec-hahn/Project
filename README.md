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

Lab bring-up is underway. An OpenAI connectivity check passed directly from CTRL01 and through the relay from AGENT01. Manual file checks confirmed that the Finance role account could read its assigned Finance report and was denied access to HR. The project has collected 27 research references for review. Comparative trials and results are pending.

## Project files

- [Research sources and descriptions](resources/sources/README.md)
- [Four-VM lab plan](lab-setup.md)
- [Progress log](progress-log.md)

## Planned next steps

1. Review the closest related studies and refine the research question.
2. Select and record the exact model versions and experimental settings.
3. Complete the lab build record and fictional company dataset. Verify the Finance role and task-specific access against two Finance reports.
4. Implement controlled tools, permission checks, and action logging.
5. Pilot tasks and define expected outcomes and required permissions.
6. Run repeated comparisons across models and permission configurations.
7. Analyse security outcomes alongside task completion and document limitations.


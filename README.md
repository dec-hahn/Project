# AI Agent Permissions and Least Privilege

## Project aim

Investigate whether least-privilege controls reduce unnecessary or unintended actions by AI agents while still allowing them to complete legitimate tasks.

## Planned experiment

Compare agents powered by models from OpenAI, Anthropic (Claude), and Google (Gemini) using one shared agent framework. Exact model versions have not yet been selected.

Each agent will receive the same tools and repeatable tasks inside a controlled Linux virtual machine containing fictional company documents. Tools will support controlled file operations, and the framework will log requested actions and permission decisions.

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

The project is at the planning and literature-gathering stage. An initial list of 27 sources has been collected with brief descriptions. Implementation and experimental results are not yet documented in this repository.

## Project files

- [Research sources and descriptions](resources/sources/README.md)
- [Progress log](progress-log.md)

## Planned next steps

1. Review the closest related studies and refine the research question.
2. Select and record the exact model versions and experimental settings.
3. Build the isolated test environment and fictional company dataset.
4. Implement controlled tools, permission checks, and action logging.
5. Pilot tasks and define expected outcomes and required permissions.
6. Run repeated comparisons across models and permission configurations.
7. Analyse security outcomes alongside task completion and document limitations.

Only fictional test data and non-secret project materials should be included here. API keys belong outside the repository.


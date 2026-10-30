# Progress Log

## 30 October 2026 — Four-VM lab architecture agreed

- Selected a Windows domain controller, Windows file server, Windows agent workstation and Ubuntu experiment controller/log collector.
- Replaced the original single-Linux-VM plan with an AD-managed company file environment.
- Recorded machine sizing, security boundaries, build order and pilot acceptance checks in lab-setup.md.
- Confirmed Windows 11 as the host operating system and VMware as the virtualisation platform; the exact VMware product/version remains to be recorded.
- Revised initial allocations for sequential, API-based trials: DC01 and FS01 each receive 2 vCPU and 2 GB RAM; AGENT01 receives 2 vCPU and 4 GB RAM; CTRL01 receives 2 vCPU and 2 GB RAM.
- Planned virtual disks: DC01 60 GB; FS01 60 GB OS plus 40 GB data; AGENT01 80 GB; CTRL01 60 GB. Total guest allocation: 8 vCPU, 10 GB RAM and 300 GB virtual disk capacity, excluding snapshots and backups.
- These are lean starting allocations. Pilot runs will check memory pressure, timeouts and logging reliability before resources are fixed across experimental conditions.
- Deployment has not started. Next: record the VMware version, confirm Windows licensing, then provision the isolated network and DC01.

## 19 October 2026 — Research documentation prepared

- Recovered the project plan from earlier planning discussions.
- Documented the proposed comparison of OpenAI-, Claude-, and Gemini-powered agents.
- Documented broad-access, role-based, and task-specific permission configurations.
- Prepared an initial list of 27 related research sources with brief descriptions.
- Prepared a project overview and progress log for sharing with the teacher on GitHub.

Current stage: planning and literature review. No experimental results have been recorded yet.

Next: review priority papers, select exact model versions, and begin the test-environment prototype.

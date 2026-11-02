# Four-VM experiment lab

30 October 2026. Status: planned; no machines deployed yet.

## Scope

Evaluate AI agent behaviour when accessing centrally managed company file resources under broad, role-based and task-specific permissions. This represents an Active Directory-managed company file environment. Cloud identity, availability testing and other business applications are outside the initial scope.

## Machines

| Name | Operating system | Starting allocation | Responsibilities |
| --- | --- | --- | --- |
| DC01 | Windows Server 2025 Standard | 2 vCPU, 2 GB RAM, 60 GB disk | Active Directory Domain Services, DNS, users, groups and Group Policy |
| FS01 | Windows Server 2025 Standard | 2 vCPU, 2 GB RAM, 60 GB OS + 40 GB data | Domain-joined SMB file server, departmental documents, share and NTFS permissions, file auditing |
| AGENT01 | Windows 11 Enterprise | 2 vCPU, 4 GB RAM, 80 GB disk | Domain-joined workstation, shared agent framework and model API calls |
| CTRL01 | Ubuntu Server 24.04 LTS | 2 vCPU, 2 GB RAM, 60 GB disk | Trial coordination, tool logs, collected Windows audit events and outcome evaluation |

Host: Windows 11 using VMware (exact product/version to be recorded). Allocations are lean starting estimates for sequential trials, not guaranteed workload minimums. Total: 8 vCPU allocations, 10 GB guest RAM and 300 GB virtual disk capacity, excluding backups and snapshots. Model inference is assumed to use external APIs. Use lightweight log collection rather than a heavy analytics stack. Windows Server Desktop Experience at 2 GB may be slow; increase individual servers to 4 GB if pilot measurements show memory pressure. Keep allocations consistent across experimental conditions.

## Security and experimental boundaries

- Use an isolated virtual network, with controlled outbound access for updates and model APIs. Do not bridge the lab into a real company domain.
- Administer from the host using separate administrative credentials; do not expose those credentials to the agent runtime.
- Use fictional Finance, HR, Sales and IT documents and identities.
- Broad access means access to experimental documents, not domain or local administrator privileges.
- Keep the framework, tools, dataset and tasks identical across permission conditions. Enforce differences through the effective permissions of each trial identity.
- Role-based identities receive departmental group access. Task-specific identities receive only the resources and operations defined in the task permission manifest.
- Distinguish read, create, modify and delete operations. Verify both SMB share and NTFS effective permissions.
- Run file operations under the assigned trial identity. Do not route them through a privileged service account that bypasses that identity's restrictions.
- Keep CTRL01 results inaccessible for modification by experimental identities. Keep credentials and API keys outside version control.
- Record requested tool actions separately from server-confirmed access. Configure audit policy and resource audit rules explicitly; validate successful and denied access collection.
- Record exact OS builds, updates, framework dependencies, model identifiers, task versions and permission state for reproducibility.

## Build sequence and acceptance checks

1. Select the hypervisor and confirm host OS, licensing and installation media. Record virtual network layout, domain name, IP addresses and DNS configuration before deployment.
2. Build DC01 and create the isolated domain, departmental groups, administrative identities and experimental identities. Confirm domain DNS and time synchronisation.
3. Build and domain-join FS01. Create the fictional dataset, departmental shares and permission manifest. Check allowed and denied operations manually using experimental identities.
4. Build and domain-join AGENT01. Install the shared framework and tools. Confirm operations use the intended domain identity and the agent cannot administer the domain or file server.
5. Build CTRL01. Implement trial coordination and select a Windows-event collection mechanism compatible with the Linux collector. Confirm that a known successful read and a known denied read can be correlated with tool requests using trial IDs and timestamps.
6. Implement reset and validation procedures for document contents, permissions, group membership and workstation state. Start fresh logon sessions when changing identities or membership; account for cached credentials and existing SMB sessions. Do not independently revert domain machines without a tested, coordinated recovery procedure.
7. Pilot one legitimate task and one attempted cross-department access under all three conditions. Verify task outcomes, effective permissions and retained logs before scaling up.

## Decisions still required

- Framework, exact model versions and API credential handling.
- Task-specific permission provisioning and revocation mechanism.
- Windows audit forwarding/collection implementation and retention period.
- Task set, expected outputs, permission manifests and repetition counts.

## Vendor references

- [Windows Server 2025 installation media and evaluation information](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2025)
- [Windows 11 Enterprise evaluation](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-11-enterprise)
- [Active Directory Domain Services overview](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/active-directory-domain-services)
- [Ubuntu lifecycle](https://ubuntu.com/kernel/lifecycle)


# My project progress

## 15 November 2026

I got all four VMs up and communicating in the lab. DC01 hosts the Active Directory domain, FS01 and AGENT01 are joined to it, and CTRL01 is connected to the lab network.

I tested the file permissions and auditing. The Finance test account could open the assigned Finance report and was denied access to HR. I also tested the file-access auditing options and confirmed they worked.

I tested the relay from AGENT01 through CTRL01 with an OpenAI API key supplied on CTRL01. I got HTTP 200 and `OK` back on AGENT01.

Next I need to add a second Finance report and compare what the Finance role and task-specific accounts can open. I also need to check that I can match file audit events to the trial logs before running the first comparison.

## 14 November 2026

I checked that AGENT01 could reach CTRL01 over the private lab network. Then I tested a direct OpenAI API call from CTRL01 using `gpt-5-nano`. I got HTTP 200 and the reply `OK`. I also tested the relay from AGENT01 through CTRL01 and got the same response back on AGENT01. I entered the API key on CTRL01 for the test.

On FS01, I set up the Finance and HR test files, including a fictional payroll file. I signed in with the Finance test account and confirmed I could read the assigned Finance report. I also tried accessing HR with the same account and confirmed access was denied.


## 2 November 2026

I updated the [lab setup notes](lab-setup.md) with how I plan to set up the file permissions, check the audit logs and reset the lab between runs. I also wrote down the decisions I still need to make, including which agent framework and model versions to use and how many times to repeat each task.

## 30 October 2026

I settled on a four-VM lab on my Windows 11 host using VMware. I moved on from the original single Linux VM idea because I wanted the lab to work like a company file network managed through Active Directory.

| VM | What I plan to use it for | Starting allocation |
| --- | --- | --- |
| DC01 | Windows domain controller for users and groups | 2 vCPU, 2 GB RAM, 60 GB disk |
| FS01 | Windows file server for the fictional department files | 2 vCPU, 2 GB RAM, 60 GB OS disk plus 40 GB data disk |
| AGENT01 | Windows workstation for running the agents | 2 vCPU, 4 GB RAM, 80 GB disk |
| CTRL01 | Ubuntu server for coordinating tests and collecting logs | 2 vCPU, 2 GB RAM, 60 GB disk |

I planned for 8 vCPU, 10 GB of guest RAM and 300 GB of virtual disk space in total, before snapshots and backups. I kept the starting allocations low because I plan to run the tests one at a time and use model APIs. I’ll check memory use, timeouts and logging during the pilot. At this point I still needed to record the exact VMware version and confirm Windows licensing.

## 19 October 2026

I pulled together my project idea and wrote out how I want to compare agents using OpenAI, Claude and Gemini. I want to see how they behave with broad file access, access based on their department and access limited to the task they’ve been given.

I collected [27 sources](resources/sources/README.md) and added a short description for each one so I could decide which to read first. I also prepared the project overview and progress log to share on GitHub.

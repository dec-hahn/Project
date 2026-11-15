# My project progress

## 14 November 2026

I checked that AGENT01 could reach CTRL01 over the private lab network. Then I tested a direct OpenAI API call from CTRL01 using `gpt-5-nano`. I got HTTP 200 and the reply `OK`. I also tested the relay from AGENT01 through CTRL01 and got the same response back on AGENT01. I entered the API key on CTRL01 for the test.

On FS01, I set up the Finance and HR test files, including a fictional payroll file. I signed in with the Finance test account and confirmed I could read the assigned Finance report. I also tried accessing HR with the same account and confirmed access was denied.

My next step is to add a second Finance report. I want to check that the Finance account can open both reports and that the task-specific account can only open the assigned one. After that I need to check that the audit logs capture the allowed and denied actions before I run the first comparison.

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

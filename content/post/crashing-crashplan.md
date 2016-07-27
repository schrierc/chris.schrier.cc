+++
title = "Crashing crashplan"
date = 2013-02-08T13:31:00Z
updated = 2013-02-08T13:31:37Z
tags = ["backup", "crashplan"]
blogimport = true 
[author]
	name = "Chris Schrier"
+++

I'm evaluating CrashPlan for performing backups of my home computers. It worked
flawlessly for my smaller files (Photos, documents) but started crashing when I
added my video directory.

After a quick search I discovered that the CrashPlan backup service was exceeding its memory allocation. It was trivial to
change the allocation from 512m to 1024m:

*  Stop the CrashPlan Backup Service
*  Launch notepad as Adminitrator
*  Edit `C:\Program Files\CrashPlan\CrashPlanService.ini`
*  Change `-Xmx512m` to `-Xmx1024m`

Answer from http://homeservershow.com/forums/index.php?/topic/3978-is-your-crash-plan-crashing

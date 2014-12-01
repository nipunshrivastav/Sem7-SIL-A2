Sem7-SIL-A2
===========
Project 2: Monitoring Systems for Intrusions (150 points)
Project 0 helped you understand how an attacker might probe a system for vulnerabilities by setting up an attacker machine with all the modern tools (Kali Linux) and another machine with known vulnerabilities (metasploitable). This project will help you understand how defenders work.

As before, you'll have 2 VMs, one of which you'll probe for vulnerabilities and attack. However, this time you'll install/create/use a variety of defensive tools. You can create these VMs on Baadal. Please remember that you'll need to use the CSE instance of Baadal, not the CC instance! The VM under attack should run windows.

As we have discussed in class, an attack manifests itself in many ways. There could  be a change in the content, endpoints, and distribution of the network traffic. There could be a change in how a subverted process executes in terms of memory consumption or instructions executed or libraries used or disk usage or ... Note that we're talking about a "change”, which ipso facto implies that we understand what the normal behavior of the process is. This is the issue of anomaly detection that we've discussed in class.

You will collect a variety of these indicators, to minimally include

    Network Traffic

    Memory Consumed by the attacked process

    DLLs and registry objects used

    CPU usage 


There are a variety of monitoring tools on Windows that can give you this information, such as those in the SysInternals suite (http://technet.microsoft.com/en-us/sysinternals/default). You can also use wireshark to capture network traffic. Using this tools, characterize the behavior of some standard process (say Calculator) that is normally used and innocuous.  This characterization should be in terms of averages and ranges of the various measured parameters that are numerical, and enumeration of those parameters (DLLs) that are not.

For attacks, use the Social Engineering Toolkit, which is a part of Kali Linux.  Set up a situation where a user downloads a corrupted pdf file, runs it under a vulnerable version of Adobe Reader , and gives user a meterpreter shell (http://www.offensive-security.com/metasploit-unleashed/About_Meterpreter). This is built into SET as the Adobe PDF Embedded EXE Social Engineering attack. Migrate the meterpreter shell to the process you had characterized earlier. Now measure those same parameters.

Create a Display that shows all the parameters you are measuring. How you show/visualize this is upto you, the more informative the better. Whenever the parameter "deviates” from the normal that you had measured, make the display show an alert condition with information. Again, you can decide how to measure the deviation. When you do this successfully created a Security Incident/Event Monitoring (SIEM) System! Analyze your system and report whether it detects attacks, and which elements seem the most indicative of attacks.

As an additional defense, install snort (http://www.snort.org/) with the default ruleset and see if it detects your attack. (75 points)


In addition to the above, you'll see if a machine learning system can be used to automatically flag an attack. To do this, use samples of the measured values when the process is running normally, and when it has been subverted to run meterpreter. Each of these samples can be labelled as Safe and Attack respectively. Use some standard ML toolkit (e.g Weka -- http://www.cs.waikato.ac.nz/ml/weka/ or Orange -- http://orange.biolab.si/ or R -- http://www.r-project.org/) to use Support Vector Machines to try and classify your data. Report on how well the system performs using standard measures such as accuracy, false positives, Area under ROC and so on. A key trick here will be to figure out how to normalize numerical data (think z-normalization) and how to encode enumerated data.

Here are some references for everyone.

    Wenke Lee and Salvatore J. Stolfo. 2000. A framework for constructing features and models for intrusion detection systems. ACM Trans. Inf. Syst. Secur. 3, 4 (November 2000), 227-261. DOI=10.1145/382912.382914 http://doi.acm.org/10.1145/382912.382914

    Shah, H.; Undercoffer, J.; Joshi, A., "Fuzzy clustering for intrusion detection," Fuzzy Systems, 2003. FUZZ '03. The 12th IEEE International Conference on , vol.2, no., pp.1274,1278 vol.2, 25-28 May 2003 doi: 10.1109/FUZZ.2003.1206614

    Paxson, Vern. "Bro: a system for detecting network intruders in real-time." Computer networks 31.23 (1999): 2435-2463.

    Mathews, M. Lisa, Paul Halvorsen, Anupam Joshi, and Tim Finin. "A collaborative approach to situational awareness for cybersecurity." In Collaborative Computing: Networking, Applications and Worksharing (CollaborateCom), 2012 8th International Conference on, pp. 216-222. IEEE, 2012.


Submission

Describe the concrete steps you took to complete the project in sequential manner. Provide screenshots and data that you collected wherever necessary. In addition, write a short summary (300 words) describing what you think are the cool takeaways from the project. All these files are to be submitted in a single zipped folder which is named with your entry number.

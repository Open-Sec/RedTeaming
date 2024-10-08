# Red Team Framework by Open-Sec

Once the difference between Threat Emulation and Adversary Simulation is clearly understood, this framework was developed by the Open-Sec team as a way to standardize the actions carried out during the red teaming operations that we carry out and to have a means of communication and integration of the red teamers and their work.

Also, it is important to consider what the main objectives of a red teaming exercise are, which are to measure the:
- TTD (Time To Detect): Time to Detect
- TTM (Time To Mitigate): Time to Mitigate

It is important to recognize that Mitre has popularized the TTP (Tactics, Techniques, Procedures) terminology through its ATT&CK framework (https://attack.mitre.org/).
- At the same time, it is important to be clear about some aspects of the red teaming field:
- An attacker will not use the documented TTPs that a Blue Team will take as a reference, at least not use them as they have been documented exactly. It would be absurd for attackers to do what defenders expect.
- An attacker can use TTPs as a reference, but never follow them strictly, especially since not all organizations are the same and their levels of maturity in security management are not the same either.
- A framework like ATT&CK is very suitable for carrying out Threat Emulation exercises that can start in the form of "table top exercises" and conclude with real operations for specific scenarios and cases as exercises that accompany the maturity of security management.

There are several frameworks for red teaming, some more developed than others and some based on specific sectors. All of them aim to establish clear and specific steps in the management of red teaming exercises and their results.

Initially, only the graph shown below was applied and independent documents (in markdown format) have been developed that are shared among red teamers.
Additionally, this framework has been used in the training provided by Open-Sec to, implicitly, guide the red teaming exercises appropriately among the participants. This repository is a first effort to share this documentation, but in an organized way.

**It is not intended to be a complete guide or a book or a methodology or a framework that includes everything that exists and what is yet to come, it is only a set of information to refer to by a sequential order of steps and some ideas that are modified over time (either due to obsolescence or improvements).**

1. Verification of Proper Tactics. (https://github.com/Open-Sec/RedTeaming/blob/main/Tactics.md)
2. Definition of Techniques. (https://github.com/Open-Sec/RedTeaming/blob/main/Techniques.md)
3. Execute Procedures. (https://github.com/Open-Sec/RedTeaming/blob/main/Procedures.md)
4. Real Goal. (https://github.com/Open-Sec/RedTeaming/blob/main/Goal.md)


![Red Teaming Framework by Open-Sec](https://github.com/Open-Sec/RedTeaming/blob/main/redteaming-framework-2.png)

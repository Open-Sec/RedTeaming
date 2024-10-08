# DEFINITION OF TECHNIQUES

This stage consists of the purely technical planning of the execution of the operation and exact definitions must be obtained on how to proceed during the **EXECUTION OF PROCEDURES**. Although this may seem purely methodological, it is not; it is only about actions that must be conducted because it is not possible to experience when the actions of the current operation are being executed. Any action that generates an alert can determine the partial or total failure of the operation and it is very important to never underestimate the adversary (which for the red team is the blue team or those who defend the evaluated organization).

With the information worked on in the previous stage of **VERIFICATION OF PROPER TACTICS**, we will proceed to **IDENTIFY VULNERABILITIES** that allow the attacks of the operation to be initiated or, at least, determine what the possible attack vectors are. This requires analyzing details that may even require starting to perform actions that generate traffic to the resources of the evaluated organization, but, taking into account that this is not a pentest and scans of any kind should not be considered (at least not in the indiscriminate way that they are used during a pentest).

**ATTACK VECTOR DESIGN** determines how, with what, and when vulnerability exploitation actions or sequences of steps that allow obtaining the current objective (for example, the initial compromise) and the red teamers required for each scenario will be carried out.

**TECHNIQUE REVIEW** is the final validation and confirmation that allows the move to **PROCEDURES EXECUTION** and can determine questions to the identified vulnerabilities and the designed vectors that require optimization, adding new vulnerabilities/vectors or discarding some.

## IDENTIFY VULNERABILITIES

Vulnerabilities identification as such is complex at this point because it can determine the execution of actions that generate traffic (even if it is light) and that could be detected, identified and mitigated. This is so complicated that, for example, in the case of a Full Compromise operation, it can make one of the Initial Compromise options (also called Initial Access) end up being unusable and even more so when it is conducted in frequently monitored scenarios such as those involving services on servers (whether containers or virtual machines or physical servers) or user machines (whether they are users of IT areas, local or remote) or physical security access controls.

On the other hand, there may be situations where certain controls no longer need to be identified, but the information on the targets to be used is not easily obtainable. In the case of an Assumed Breach scenario, the access controls to a private network are assumed to be breached, but at the same time it may be necessary to analyze elements for which information could not be obtained in the **RECON** module because it is highly confidential (but not invulnerable) or, simply, because it is considered something so "worthless" that it is handled "internally" and it turns out that this element becomes a perfect springboard to continue with the attack.

The best position in this module corresponds to:

- Perform natural handshake processes with the exposed services.
- Consider failures in functionalities such as escape sequences from sandbox-type environments (such as those used in thin client services).
- Use disclosed credentials to verify that they are still valid (do not start trying to list everything because each action may be audited, even the authentication performed with the disclosed credentials).
- Determine whether the applications found can or should lead to some interaction with other resources and services that allow obtaining the stated objective (this can be done easily when dealing with common/horizontal applications, with non-common/vertical applications it will have to be based on what was obtained during the previous stage and if there is no information on this, it will be unlikely to be used unless the use of components with vulnerabilities is identified, but that is no longer using applications as a means but exploiting vulnerabilities in base software).
- Analyze the controls regarding collaboration services.
- Analyze physical access controls to facilities and offices.
- Analyze access controls to wireless networks.

## DESIGN ATTACK VECTORS

Taking the Initial Compromise action is always easier as an example for this module:
- If the attack vector is going to be a web application, it may be a simple CMS or an application developed specifically for the organization. It may have an automatic self-registration option or a manual registration process may be required (such as when dealing with a banking application). This is necessary in the sense that the vulnerability that allows the initial compromise may require going through an authentication process and has social engineering implications.
- If the attack vector is an internal-use web application and there are no perceived opportunities for success with social engineering, options may have been defined based on failed access controls in related components such as exposed source code, poorly made cloud configurations, disclosed credentials, exposed development and/or QA instances with vulnerabilities or access control flaws, authentication/access recovery interfaces subject to dictionary attacks, etc.
- If the attack vector will be carried out through services exposed by servers, it is necessary to consider not only the identification of exploitable vulnerabilities but also inappropriate uses of functionalities.
- If the attack vector will be the user equipment, the ways to successfully deliver the malware will be those that will require the greatest effort because they range from determining the conditions required for distribution (phishing, physical, etc.) to how to evade EDR type protections that are included in the base operating system and those added as a complement and/or total/partial replacement.

The determination of the forms of evasion of protections that are going to be used is vital and situations where there are several and they are linked and monitored correctly must be considered. Therefore, this stage must define exactly what will be used to exploit the identified vulnerabilities (tools, exploits, scripts, etc.) or what techniques will be used and the required adjustments or whether something must be created (yes, here there is time and the effort is rewarded for the creation of exploits or scripts or tools). As can be inferred, this stage includes laboratory tests developing the scenarios that will be put into execution and **EXERCISING THEM**.

Also, it can be inferred that so many skills and experiences are required that it is required to apply to the **TEAM** part of Red Team no matter what and it is the best time to incorporate the necessary red teamers. Their participation can be partial (during a specific stage and/or module or during the entire operation). This does not imply that sooner or later they have not been or are not consulted, but their formal incorporation adds the responsibility of delivering results.

The resilience aspect (the most popular term since the pandemic) is important because it would not be smart, for example, to have defined a single vector for an Initial Compromise and if it is detected/mitigated, the failure of the operation is determined. However, this leads to another aspect that is rarely exercised in an adversary simulation, but is used in real attacks: attacking other organizations related to the evaluated organization as a means of obtaining successful attacks. In the world of red teaming, this can occur in corporations or business groups, but it is not so common unless there is an excellent level of maturity in security management at the corporate or group level.

## REVIEW TECHNIQUES

This part is the final validation and the best recommendation is that it is conducted by the assigned Red Team Leader with the support of a red teamer who has not participated in the previous stages. This way, better feedback can be obtained that leads to rethinking or continuing to the next stage.

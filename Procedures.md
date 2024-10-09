# EXECUTE PROCEDURES

This is the stage of executing the operation's actions and there are many variants due to several factors that can be summarized in two:
Due to the results of the previous stages.

Due to the type of scenario to be developed.

In the simplest form, the scenarios to be developed depend on the specific requirement of the organization to be evaluated or the understanding of the red team regarding what is most appropriate. It can be more complex if recurring or continuous services are considered and even more so in permanent ones.

Three typical scenarios are:
- Full Commitment
- Assumed Breach
- Customized Breach
  
Here you can see a difference with previous stages since the **ATTACK VECTOR DESIGN** gives off two parallel sequences:
- **INITIAL COMMITMENT**
- **INSTALLATION**

Beyond the considerations indicated above, it is always considered that there will be an **INITIAL COMPROMISE** which is the starting point of all the actions of the current exercise even if it does not correspond to a Full Commitment.

The **INSTALLATION** module consists of all the actions necessary to have a Command and Control Center (C2) in the proper way. The simplicity or complexity of it was defined in the **VERIFICATION OF PROPER TECHNIQUES** stage.

The other two modules, **LATERAL MOVEMENT** and **STAY AND EXFILTRATE** are given as a natural, but ordered consequence of the previous modules.
It is not intelligent to think that having obtained a "foot" (however highly privileged) inside an organization, one will not consider entering with the entire "body" and this is what gives rise to the displacement in a natural way, but, it is an action that allows obtaining the desired permanence within the organization for actions such as the exfiltration of information.


## INITIAL COMPROMISE

Regardless of the scenarios to be developed, there should always be several **INITIAL COMPROMISE** alternatives and, if possible, more than one of the same type. The reasons are diverse, but, again, they can be summarized in two:
- No matter how much planning has been done, some conditions can change while the actions of the operation are being executed.
- Distraction, such as when an "attack" is generated using insecure protocols that send/receive everything in plain text and at the same time a real attack is executed.
  
Listing all the possible types of **INITIAL COMPROMISE** not only goes beyond this framework but would be pretentious in trying to pigeonhole the reality of organizations into a typology. Being somewhat philosophical, the Hegelian dialectic is perfectly applied here, summarized, in a colloquial way, in the fact that no one bathes twice in the same river. However, we can see that the most common are:
- Through web applications. Mainly in the base software used in them that leads to RCE or vulnerabilities in the implementation of functionalities that allow obtaining total control of the information. As added value, the monitoring of incidents that has evolved is that which is given at the infrastructure level, the application level is outdated and in no way integrated with the rest of the security management in an adequate manner.
- Through cloud services that lead to the core of the organization because it is still based on legacy equipment by permanent decision or because they are in migration. Other conditions of cloud services are not ethically exploitable, but the world of real attacks can make use of them as in the cases of insecure SaaS.
- Escape from the "sandboxes" imposed by thin clients.
- Remote access via VPN (especially webvpn).
- Wireless networks that radiate their signal outside the physical perimeter of the offices of the evaluated organization.
- Client Side Attacks (CSA) that start with actions such as phishing in a more common way.
- Social engineering including physical intrusion.

## INSTALLATION

This module must ensure that the operation has at least one reliable C2 and attack infrastructure, and that this determines that installations, configurations, high availability must be implemented, and threat management actions must be carried out by the evaluated organization.

There is no C2 that is suitable for every operation, but there are some functionalities that are required, such as allowing resilience in the implants when they are detected/mitigated, providing concealment mechanisms, allowing customization at any level, including the modification/addition of payloads/implants and their forms of concealment. The latter is very important because C2s are often expected to be an accurate, successful and inexhaustible source of payloads, and their function is not to be anything other than a form of support for the ongoing operation.

However, all this infrastructure can fail or be "mitigated" and the need to quickly have a new one becomes evident. This is what leads us to have to automate the **INSTALLATION** process through IaC or, more properly, to use DevOps and OpSec.

In the aspect of complementary infrastructure, there are diverse requirements that depend on each type of action. For example, if phishing is an option, it is necessary to configure services, domains, generate reputation, etc. well in advance of the execution of the sending of messages and that determines infrastructure that must be so reliable that it overcomes the controls of modern email services.

## LATERAL MOVEMENT

The forms of lateral displacement based on vulnerabilities in MS Windows systems are widely documented and controlled at the same time. The same occurs with failures in base services such as Active Directory and they are usually more frequent.

On the other hand, systems based on Linux or MacOS are usually perceived as less insecure in terms of software vulnerabilities, but equally prone to configuration failures or inadequate maintenance. In this area, favorable conditions will be given for lateral displacement that do not depend on updates or secure configurations because there is embedded technology that will not progress in the security aspect due to the manufacturer's decision. Thus, the components of a video surveillance system based on a reduced version of Linux help a lot in this module.

Internal applications are also a source of support in lateral displacement because they are usually considered to be less risky due to their "location" condition in a private network, which allows the use of obsolete versions of base software or less (or no) effort has been made to make it secure or they reside in legacy systems.


## STAY AND EXFILTRATE

At this stage, actions are executed to allow persistence in the computers where the implants have been placed (for example when they are rebooted) and to maintain the penetration obtained (if a zombie/agent/implant is discovered and eliminated). There are various techniques to allow permanence to be obtained and the best known is the one that implements a daisy chain mechanism.

Exfiltration is a "final" step in this whole stage, that is, since the objective of the adversary simulation is to behave as close as possible to the real attacker, a way must be provided to extract the data to which access is being obtained. Knowledge about the use of specific protocols/services such as DNS, ICMP, etc. to execute exfiltration is well disseminated. Therefore, what can be specified are the means used. For example, it is very common for internal DNS servers used for AD to have query forwarding implemented towards the Internet.

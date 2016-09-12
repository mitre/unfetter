---
layout: flat
title: About
---

The Unfetter project is a joint effort between [The MITRE Corporation](https://www.mitre.org) and the United States National Security Agency (NSA).

Unfetter is based on MITRE’s [Adversarial Tactics, Techniques, and Common Knowledge]({{site.attack_url}}) (ATT&amp;CK) threat model, the associated [Cyber Analytics Repository]({{site.car_url}}) (CAR), and a graphical user interface known as the [Cyber Analytic Repository Exploration Tool]({{site.caret_url}}) (CARET) that connects CAR and ATT&amp;CK. Information summarizing ATT&amp;CK, CAR, and CARET may be found below.

## Contemporary Detection Shortcomings

Contemporary detection methodologies focus on extensive use of anti-virus, commercial threat intelligence or other threat intelligence sharing products, and indicators of compromise (IOCs). Unfortunately, these focus areas are not a panacea for the defender against the adversary. Despite defender use, adversaries who are able to bypass or overcome these common defenses typically encounter a minimally protected network at the host level once inside. Anti-virus can be defeated by adversaries testing their malware in advance against popular security products or malware databases, ensuring the ability to overcome detection. Commercial threat intelligence products identify only a subset of adversary techniques and are only as good as the quality of information available. IOCs judge the presence of malicious activity by detecting known bad objects on a computer; however, objects only identify past adversaries’ activities. Objects are useful to identify individual adversaries from past compromises and behaviors, but they are not useful to detect unknown actors that may eventually focus their efforts on compromising networks in the future. In the real world, defenders don’t track objects, they track behaviors.

## A New Defensive Paradigm

A paradigm shift is required to secure enterprises more effectively. This shift accepts that today’s adversaries are able to penetrate the network boundary despite our current technologies and accepts the need for additional host-based technologies and hyper-sensing capabilities. In addition, it accepts that we must move from IOCs to indicators of attack (IOAs) to understand the behaviors of the adversary in order to detect the unknown future actor.

This paradigm shift to IOAs introduces a subtle difference in how sensors must collect data. IOAs describe both actors and atomic actions; therefore, IOA detection can only be performed on data that is collected by capturing actions as they are performed. Some call this kind of collection a real-time sensor; however, the term "real-time" has been misused to the point of being meaningless in the context of endpoint sensing. Scanning is not adequate because a scan observes the present state of objects, capturing neither actions nor actors. Although in some cases an action may be inferred from the observation of objects on a system (a new file exists; therefore, someone must have created it) or the system may cache actors and actions (a running process tree), these pictures are incomplete because they either cannot capture the actor, or they are prone to missing actions that occur between scans. This situation cannot be fixed by simply scanning at more frequent intervals, because even "continuous" scanning cannot capture every atomic action: to do so would require a scan after every single operation on the computer, because a scan only captures discrete points in time, not a continuous stream. Trying to collect IOAs by scanning misses the myriad actions that happen on the system between scans. For this reason, sensors that seek to detect IOAs must collect data in real time. Conversely, any sensor that only scans is blind to IOAs.

This shift from scanning to real-time detection, from IOC to IOA, is powerful because real-time detection also provides the opportunity for prevention. If a real-time sensor captures an action while it is happening and determines the action is bad, it can prevent the bad action from occurring, something that scanning systems cannot do.


## Threat-based Security
MITRE’s threat-based approach to network defense is guided by five key principles:
<ul style="list-style-type:none">
<li style="margin: 10px 0"><i>Principle 1: Detection Post-Compromise</i> - Perimeter and preventative defenses will fail to stop persistent attackers; post-compromise detection capabilities are necessary.</li>

<li style="margin: 10px 0"><i>Principle 2: Focused on Behavior</i> - Signatures and indicators are useful but can be circumvented; sophisticated defenses should incorporate detecting adversary behavior.</li>

<li style="margin: 10px 0"><i>Principle 3: Threat Model Based</i> - An accurate and well-scoped threat model is necessary to ensure that detection activities are effective against realistic and relevant adversary behaviors.</li>

<li style="margin: 10px 0"><i>Principle 4: Iterative by Design</i> - The attack tool and technique landscape is constantly evolving; a successful approach to security requires constant, iterative evolution and refinement of security models, techniques, and tools. In an ideal scenario, this iteration is done in concert with the larger community of interest.</li>

<li style="margin: 10px 0"><i>Principle 5: Developed in a Realistic Environment</i> - Analytic development and refinement should be done in a network environment that is as realistic as possible. This includes sensor noise generated by third-party software and real users if feasible. Whenever possible, detection capabilities should be tested by threat emulation in the realistic environment.</li>
</ul>

## Adversarial Tactics, Techniques, and Common Knowledge (ATT&amp;CK)

Adversarial Tactics, Techniques, and Common Knowledge (ATT&amp;CK) is a model and framework for describing the actions an adversary may take while operating within an enterprise network. The model can be used to better characterize and describe post-compromise adversary behavior. It both expands the knowledge of network defenders and assists in prioritizing network defense by detailing the post-compromise (post-exploit and successful access) tactics, techniques, and procedures (TTPs) advanced persistent threats use to execute their objectives while operating inside a network.

ATT&amp;CK incorporates information on cyber adversaries gathered through MITRE research, as well as from other disciplines such as penetration testing and red teaming, to establish a collection of knowledge characterizing the post-compromise activities of adversaries. While there is significant research on initial exploitation and use of perimeter defenses, there is a gap in foundational knowledge of adversary process after initial access has been gained. ATT&amp;CK focuses on TTPs adversaries use to make decisions, expand access, and execute their objectives. It aims to describe an adversary's steps at a high enough level to be applied widely across platforms, but still maintain enough details to be technically useful.

The ten tactic categories for ATT&amp;CK were derived from the later stages (control, maintain, and execute) of the seven-stage Cyber Attack Lifecycle (first articulated by Lockheed Martin as the [Cyber Kill Chain](http://www.lockheedmartin.com/content/dam/lockheed/data/corporate/documents/LM-White-Paper-Intel-Driven-Defense.pdf)&reg;). ATT&amp;CK provides a deeper level of granularity in describing what can occur during an intrusion after an adversary has acquired access.

Each category contains a list of techniques that an adversary could use to perform that tactic. Techniques are broken down to provide a technical description, indicators, useful defensive sensor data, detection analytics, and potential mitigations. Applying intrusion data to the model then helps focus defense on the commonly used techniques across groups of activity and helps identify gaps in security. Defenders and decision makers can use the information in ATT&amp;CK for various purposes, not just as a checklist of specific adversarial techniques.

ATT&amp;CK is largely focused on Microsoft Windows enterprise networks for individual technique details. The framework and higher level categories may also be applied to other platforms and environments. 

<img src="{{ site.baseurl }}/img/attack-matrix-2.png" alt="ATT&CK Matrix" width="100%" />

## ATT&amp;CK-Based Analytics Development Method
The ATT&amp;CK-Based Analytics Development Method is the process MITRE used to create, evaluate, and revise analytics with the intent of detecting cyber adversary behavior. It was refined over years of experience investigating attacker behaviors, building sensors to acquire data, and analyzing data to detect adversary behavior. In describing the process, we use the terms white team, red team, and blue team, which we define as follows:

<ul style="list-style-type:none">
<li style="margin: 10px 0"><b>White Team</b> – Develops threat scenarios for testing defenses. Works with the red team during the cyber game to log red team activity, and answers any questions that the red team might have related to whether a given system, account, or technique is in or out of bounds for this game.</li>

<li style="margin: 10px 0"><b>Red Team</b> – The emulated cyber adversary for this cyber game. Many traditional red teams focus on highlighting vulnerabilities that need to be mitigated. This red team differs somewhat from that approach. Its goal is to perform the behaviors and accomplish the objectives outlined by the white team in order to ensure testing and validation of blue team analytics and methodology. Any vulnerabilities discovered will also be reported, but that is a secondary goal of the team.</li>

<li style="margin: 10px 0"><b>Blue Team</b> – Network defenders who use analytics to detect red team activity. It may also be thought of as a hunting team.</li>
</ul>

The ATT&amp;CK-Based Analytics Development Method contains seven steps:

<ol>
<li><i>Identify Behavior</i> - Identify and prioritize adversary behaviors from the threat model to detect.</li>
<li><i>Acquire Data</i> - Identify the data that is necessary to detect this adversary behavior. If the capability to acquire the data does not exist, a sensor must be created to collect this data.</li>
<li><i>Develop Analytics</i> - Create analytics to detect the identified behaviors with the collected data. It is also important to ensure that analytics have an acceptable false positive rate on benign environmental events.</li>
<li><i>Develop Threat Emulation Scenario</i> - The white team develops a threat emulation model based on ATT&amp;CK that includes the behaviors identified in Step 1. The scenario includes specific techniques the red team should use.</li>
<li><i>Emulate Threat</i> – The red team attempts to achieve the objectives outlined by the white team by exercising the behaviors in ATT&amp;CK.</li>
<li><i>Investigate Attack</i> – The blue team attempts to recreate the timeline of red team activity using analytics and data developed in Step 3.</li>
<li><i>Evaluate Performance</i> – White, red, and blue teams review the engagement to evaluate which analytics and sensor data the blue team was able to use to detect the behaviors in Step 1.</li>
</ol>

## The Cyber Analytics Repository (CAR)

The [Cyber Analytics Repository]({{site.car_url}}) (CAR) is a knowledge base of analytics developed by MITRE based on the [Adversarial Tactics, Techniques, and Common Knowledge]({{site.attack_url}}) (ATT&amp;CK) model and framework. CAR uses the ATT&amp;CK-Based Analytic Development methodology outlined above to create, evaluate, and revise analytics with the intent of detecting cyber adversary behavior. Development of an analytic is based on the following activities: identifying and prioritizing adversary behaviors to detect from the ATT&CK threat model, identifying the data necessary to detect the adversary behavior, creating a sensor to collect the data if necessary, and actually creating the analytic to detect the identified behaviors.

There are multiple ways to categorize analytics. The categories are not comprehensive. Since the analytics are derived from a threat model based on adversary behaviors some types of analytics are out of scope (e.g., signature, profile based). The following four types of analytics are identified in CAR:

<ul style="list-style-type:none">
<li style="margin: 10px 0"><b>Behavioral</b> - An analytic designed to detect a specific behavior used by adversaries, such as creating a new Windows service. The behavior by itself may or may not be malicious. These behaviors should map back to techniques identified within ATT&amp;CK.</li>

<li style="margin: 10px 0"><b>Situational Awareness</b> - Analytics geared toward a general understanding of what is occurring within your environment at a given time. Not all analytics need to be geared toward generating alerts on malicious behavior. Rather, it can be very beneficial for organizations to have analytics that provide general information on the state of the environment. Information such as login times doesn’t indicate malicious activity, but when coupled with other indicators can provide much-needed additional information. These types of analytics can also be helpful for monitoring the “health” of your environment (e.g., on which hosts sensors are not working).</li>

<li style="margin: 10px 0"><b>Anomaly/Outlier</b> - Detection of behavior that is not malicious but that is unusual and may be suspect. Examples are detection of executables that have never been run before or a process using the network that does not normally use the network. Like Situational Awareness analytics, these types of analytics don’t necessarily indicate an attack.</li>

<li style="margin: 10px 0"><b>Forensic</b> - These types of analytics are most useful when conducting an investigation of an event. Often forensic analytics will need some kind of input to be most useful. For example, if an analyst finds that a credential dumper was used on a host, the analyst can then run an analytic that will reveal all the users whose credentials were compromised.</li>
</ul>

Within each analytic, the following information is available:

<ul style="list-style-type:none">
<li style="margin: 10px 0"><b>Description</b> - A description of the hypothesis being tested in the analytic, including any relevant information about how alerting on this type of information would be of interest or benefit to a defender.</li>
<li style="margin: 10px 0"><b>Categorical Information (CAR analytic number, submission date, information domain, host subtypes, types, status)</b> - The analytic number for alerting and tracking purposes, whether the analytic applies to the host or network, available and applicable subtypes, the type of analytic, and the analytic's status (active or idea).</li>
<li style="margin: 10px 0"><b>ATT&amp;CK Detection</b> - A summary of the ATT&amp;CK tactic and technique the analytic covers as well as the level of coverage.</li>
<li style="margin: 10px 0"><b>Pseudocode</b> - The analytic instantiation defined using pseudocode.</li>
<li style="margin: 10px 0"><b>Unit Tests</b> - The requirements, configuration, description, and command applicable to test the analytic.</li>
</ul>

## CARET

The [Cyber Analytic Repository Exploration Tool]({{site.caret_url}}) (CARET) is a proof-of-concept graphical user interface designed to connect the groups and techniques listed in ATT&amp;CK to the analytics, data model, and sensors described in CAR. CARET is used to link adversaries, techniques, analytics, data, and sensors to develop an understanding of defensive capabilities and to aid in their development and use. In particular, CARET helps answer the following types of questions:
<ul style="list-style-type:none">
<li><b>What known adversaries:</b>
 <ul style="list-style-type:none">
  <li>… can you detect/not detect?</li>
 </ul>
</li>
<li><b>What analytics:</b>
 <ul style="list-style-type:none">
  <li>…can detect given tactics or techniques?</li>
  <li>…can detect a given known adversary?</li>
 </ul>
</li>

<li><b>What data:</b>
 <ul style="list-style-type:none">
  <li>…is generated by your sensors?</li>
  <li>…is required for your analytics?</li>
  <li>…is needed to detect a given adversary?</li>
 </ul>
</li>
<li><b>Which sensors:</b>
 <ul style="list-style-type:none">
  <li>…produce data for what analytics?</li>
  <li>…can detect particular techniques?</li>
  <li>…can detect a particular adversary?</li>
 </ul>
</li>
</ul>

### CARET Use Cases
<ul>
<li>Leadership asks an analyst where they should invest future capital in host-based analytics. An analyst uses CARET by selecting sensors to identify the types of analytics they can use and the groups and ATT&amp;CK techniques that would be covered.</li>
<li>Leadership asks an analyst what sensors they should purchase to have coverage against a particular group. An analyst uses CARET by selecting a group to understand the ATT&amp;CK techniques used by the group and the analytics and sensors that could be implemented to detect the group.</li>
<li>An analyst is trying to understand the intersection of groups and analytics on the ATT&amp;CK matrix. The analyst uses CARET to select a group, highlighting the ATT&amp;CK techniques used, then applies the analytics to develop coverage to detect the group. In addition, analysts can evaluate where there may be gaps in their analytic portfolios and concentrate investments in developing new analytics to address these gaps.</li>
<li>An analyst wonders which of all available data is the most useful. The analyst evaluates the data model options in CARET to see which objects, actions, and fields are most critical to identifying groups given a particular set of analytics or sensors. In addition, analysts can determine whether they are gathering data that is not being used effectively.
</li>
</ul>

## Unfetter

The [Unfetter reference implementation]({{site:reference_implementation}}) enables the user to apply additional offered analytics and experiment with test cases to develop more robust analytics for better detection methodologies.

While Unfetter is a project designed to help network defenders, cyber security professionals, and decision makers identify and analyze defensive gaps, the overall objective is to help the community iterate, evolve, and progress toward the broader goal of achieving greater network resiliency. Unfetter is an open-source project. Cyber resiliency, as defined by the MITRE [Cyber Resiliency Engineering Framework](https://www.mitre.org/publications/technical-papers/cyber-resiliency-engineering-framework), addressed four chief goals: anticipate, withstand, recover, and evolve. Unfetter specifically impacts cyber resiliency by addressing the need to anticipate and evolve. Through gap analysis relative to detective capabilities and the threat, Unfetter provides a mechanism to anticipate an enterprise's gaps in adversary detection. This further enables the enterprise to minimize impacts from anticipated or actual adversary attacks through smarter sensing. This advancement in sensing also enables effective decision-making and faster response times. Faster responses, implemented through automation, minimize the impact of current attacks. In addition, decision-making that utilizes learning and reasoning over time enable the system to evolve to a less vulnerable state to future attacks, especially ones similar to previous attacks. Overall, Unfetter not only impacts an enterprise's ability to anticipate attacks, but can also support other cyber-resiliency goals, such as evolution.

## Tying It All Together

The overarching process allows you to understand how each release and the core concepts on which they are based educate and inform the community as a whole. 

<img src="/img/arrow-diagram.png" width="100%" />

Use threat-based intelligence to figure out where there are gaps and redundancies within your enterprise. This is part of an iterative process:
<ul style="list-style-type:none">
 <li><b>Explore</b> - Develop questions related to adversary detection, analytic effectiveness, and sensor inputs.</li>
 <li><b>Discover</b> - Identify connections between adversary techniques, analytics, and sensors to answer those questions.</li>
 <li><b>Create</b> - Devise analytics and determine what additional data they require. Validate them with cyber games.</li>
 <li><b>Apply</b> - Use the sensors and analytics to improve your own cyber defense.</li>
 <li><b>Share</b> - Improve your defenses in concert with the broader community.</li>
</ul>

Viewing [CARET]({{site:caret_url}}) online allows you to explore the concepts of groups, techniques, analytics, data model, and sensors to understand how analytics can be used to identify adversary tradecraft. Building upon the concepts in CARET, you can discover new connections between groups, analytics, and sensors. Downloading CAR, ATT&CK, and CARET enables you to create new analytics and customize the available information for your environment. The Unfetter reference implementation allows you to experiment with analytics in a virtual environment.

<img src="{{ site.baseurl }}/img/unfetter-process-graphic.png" alt="Process for using Unfetter" width="80%" />

### Process
<ol>
 <li> Download and modify the Cyber Analytics Repository (CAR) depending on what sensors and analytics are running in your environment.</li>
 <li> Identify and assess coverage gaps between adversary techniques, analytics, and sensors using CARET.</li>
 <li> Using the insights gained in the previous step, management can make data driven decisions on where to invest time and resources based on known threats and the status of their enterprise.</li>
 <li> Create and test new analytics, adding the finished product to CAR.
  <ul style="list-style-type:none">
   <li>4a. Use the Unfetter Reference Implementation to write new analytics or experiment with existing ones. Determine what new sensors, if any, are needed.</li>
   <li>4b. Use the Reference Implementation to test the analytic and ensure it produces the appropriate output.</li>
   <li>4c. Perform red team and blue team cyber games, ideally in your live environment, to validate the analytics. See <a href="#attampck-based-analytics-development-method">ATT&CK-Based Analytics Development Method</a> above.</li>
  </ul>
  </li>
 <li> Share adversary behaviors, analytics, and sensors with the broader community. Use what others share as input to drive discovery within your enterprise.</li>
</ol>


---
layout: flat
title: Getting Started
---

## Enterprise Defense Challenges

Today’s decision makers and computer and network defense (CND) professionals face an environment with several key challenges:

<ul style="list-style-type:none">
<li>
  <b>Exploration</b>
  <ul style="list-style-type:none">
    <li>Key questions behind adversary detection, analytic effectiveness, data requirements, and sensor coverage cannot be addressed without significant time and personnel investments.</li>
   </ul>
</li>
<li><b>Translation</b> 
  <ul style="list-style-type:none">
    <li>Peers within industry and CND disciplines  are unable to utilize a common lexicon to effectively communicate tradecraft and insights.</li>
  </ul>
</li>
<li><b>Evolution</b>
  <ul style="list-style-type:none">
    <li>Current anti-virus and indicators of compromise (IOCs) detection methods fail due to the advancement of adversary attack methods that bypass or overcome common defenses. Adoption of a more behavioral-based methodology can help obviate these issues.</li>
  </ul>
</li>
<li><b>Depth</b>
  <ul style="list-style-type:none">
    <li>Network defenders are unable to effectively detect and track adversaries who have breached the network perimeter due to an inability to leverage host-based sensing and rigorous analytics.</li>
  </ul>
</li>
</ul>

## Toward a Solution

[Adversarial Tactics, Techniques, and Common Knowledge]({{site.attack_url}}) (ATT&amp;CK) is a model and framework for describing the actions an adversary may take while operating within an enterprise network. The model can be used to better characterize and describe post-compromise adversary behavior. It both expands the knowledge of network defenders and assists in prioritizing network defense by detailing the post-compromise (post-exploit and successful access) tactics, techniques, and procedures that advanced persistent threats use to execute their objectives while operating inside a network.

Our methodology for better detecting adversary activity is an iterative process:
<ol>
<li>Behavior-based analytics are developed by a blue team<a href="#footnote1" id="footnote1_src"><sup>[1]</sup></a>.</li>
<li>A cyber game, or activity that tests the defensive posture of a network, is conducted whereby a red team, or group of people who emulate the adversary, conduct simulated malicious activities. The blue team then searches for the red team activities, and remnant artifacts, to test the effectiveness of the analytics.</li>
<li>Post-game, detection refinements are made and can be applied back into the model and your environment.</li>
</ol>

The [Cyber Analytics Repository]({{site.car_url}}) (CAR) is a knowledge base of analytics developed by [The MITRE Corporation](https://www.mitre.org). The analytics detect ATT&amp;CK techniques using data from various sensors.

The [Cyber Analytic Repository Exploration Tool]({{site:caret_url}}) (CARET) is a proof-of-concept graphical user interface designed to connect the groups and techniques highlighted in ATT&CK to the analytics, data model, and sensors highlighted in CAR. CARET is used to develop an understanding of defensive capabilities and to aid in their development and use.

The following image depicts deploying the Microsoft&reg; Sysmon 3.0 sensor in an enterprise. By deploying this sensor, the analytics shown enable an analyst to identify a variety of ATT&CK techniques and the groups that use those techniques. 

<img src="{{ site.baseurl }}/img/caret-screenshot.png" alt="CARET" width="100%" />

Unfetter is an open-source software project that expands upon CARET to help cyber security professionals identify and analyze defensive gaps in a more repeatable way. For more information about Unfetter, please see the [NSA Unfetter GitHub]({{site:reference_implementation}}) page.

## Experiment with the Releases
Check out our [Releases]({{ site.baseurl }}/releases) page to try out the tools.

## Additional Resources
Additional information about CAR and ATT&amp;CK to help you understand the concepts behind Project Unfetter may be found at [{{site.car_url}}]({{site.car_url}}) and [{{site.attack_url}}]({{site.attack_url}})

***
<a id="footnote1" href="#footnote1_src">1</a> A blue team consists network defenders who use analytics to detect red team (adversary) activity. They may be thought of as a hunting team.


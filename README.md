# Deploying a Security Stack
XDR, SIEM, SOAR, *etc.* ideas and general configurations that *I intend* to be deployable just about anywhere.

Modern security solutions are better equipped to guard against bad actors than older anti-virus solutions. Also by their basic philosophy they are more accessible to the uninitiated. This repository has been created to cronicle my journey through a set of available technologies in order to assist in not only deploying a helpful and intuitive security stack, but also of making the administration of my infrastructure more manageable.

My goal is *not* to provide step-by-step directions on how to stand up a service- this has already been done by many who are more qualified than I. Instead, my goal is to provide insights into how these services might be utilized, what they could be harnessed for. Often the basic description provided falls far short of the actual capabilities of the service - I will at every turn possible, alter, enhance, rectify, *and even*, ameliorate.

This is still very much a new writeup on a project that in still progressing, so please check back to see more progress.

## How it all connects:
![](flow.drawio.svg)

## 1) Firewall
[OPNSense](firewall/opnsense.md)  
[Some other Firewalls](firewalls/other.md)  

## 2) Log Management
[syslog](logging/syslog.md)  
[Graylog](logging/graylog.md)    
<!---
[Events](logging/events.md)  
--->More to come...

## 3) Endpoint Detection
[Wazuh](wazuh/wazuh.md)

## 4) Data Enrichment
[MISP](misp/misp.md)

## 5) Response Management
<!---
[IRIS](dfir-iris/dfir-iris.md)
--->Coming soon!

## 6) Response Automation
<!---
[n8n](automation/n8n.md)
[shuffle](automation/shuffle.md)
--->Coming soon!

## 7) Visualization
<!---
[grafana](grafana/grafana.md)
--->Coming soon!

## 8) Cohesion 
<!---
[Copilot](copilot/copilot.md)
--->Coming soon!

# I'd Like to Take a Moment to Thank:
These are the educators that have been pivotal in me understanding various portions of the technologies that are absolutely essential to this project. If you aren't already familiar, you're definitely missing out!

[Christian Lempa](https://github.com/ChristianLempa)  
[Techno Tim](https://technotim.live/)  
[Taylor Walton](https://www.youtube.com/@taylorwalton_socfortress)  
[Jeff Geerling](https://www.jeffgeerling.com/)  

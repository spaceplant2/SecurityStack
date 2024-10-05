# Wazuh
*Endpoint threat detection*

Knowing what is happening on all the computers in an environment is pretty necessary. Wazuh is a lightweight utility with heavyweight functionality that can also be integrated into the larger stack. I highly recommend enabling OSQuery and adding Yara rules to check for shenanigans. One of the built in functions of Wazuh allows for compliance reports based on different controls. Useful in identifying soft spots in configurations, Wazuh also supplies remedial actions for the issues found. These remedies can be then be built into an automation platform such as Ansible and applied to the entire environment. The main server's dashboard allow metrics of all sorts to be quickly viewed, and you can drill down through graphs to view events on an individual machine.

Adding OSQuery allows for functionality such as file integrity monitoring, resource reporting, and failed login alerts. Additionally, flows can be created that trigger scans utilizing Yara rules much like the functionality of traditional antivirus software. Wazuh is also well-positioned for threat hunting. But all this is just where the magic starts! Once Wazuh has collected and collated endpoint information, it is then passed back to [Graylog](../logging/graylog.md), where our sorting, enrichment, and alerting can occur. 

[Back to Main](../README.md)

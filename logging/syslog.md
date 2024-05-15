# System Logging for Nix Systems

Syslog is the genericised name for one of a few services that handle log processing. To complicate matters, SystemD has decided to replace the syslog services with systemd-journald. While there are most definitely advantages to SystemD's journaling, we still need syslog's text format and forwarding capabilities. Depending on your OS, Distro, and preferences, you may need to install -or replace- a service. If you want a comprehensive comparison of the three possible services, see [this](https://letmegooglethat.com/?q=syslog+vs+syslogd+vs+syslog-ng). For now, the quick rundown:

- syslog:
  - The original. Not a whole lot of functionality, especially for log forwarding.
- syslog-ng
  - Expanded choices for log selection and forwarding with a new config file format.
- rsyslog:
  - Expanded choices for log selection and forwarding supporting the old config file format.

For most appliances, syslog-ng and rsyslog will both be adequate since tha main need is to choose log severity and destination. More advanced configurations can be managed with both rsyslog and syslog-ng including multiple log filters each with separate, and optionally multiple, destinations. However, these complex configurations are generally unnecessary - logs are all being sent to a far more sophisticated log server so why try to reinvent the wheel?

<!---
Check out [[these configuration examples|syslog.conf]] for examples of how to get your rsyslog or syslog-ng up and running.
--->

# Syslog Configurations

## References
[Notes from qnx.com](https://www.qnx.com/developers/docs/6.5.0SP1.update/com.qnx.doc.neutrino_utilities/s/syslog.conf.html)  

# Syslog Configuration Format
## References:
[softpanorama](https://softpanorama.org/Logs/Syslog/syslog_configuration_examples.shtml)  
The simpleset and most limited format. While I don't recomment the service *per se*, this config
 format should be enuough to get any of these services up and running. Further refinement may 
 be necessary.
```
*.notice					                          /var/log/messages
*.err;*.emerg;*.crit;auth,authpriv.debug		@loghost
```

# Syslog-NG Format

## References
[from syslog-ng.com](https://www.syslog-ng.com/community/b/blog/posts/syslog-ng-101-part-4-configuration-and-testing)

The following config example explains why I don't use syslog-ng: while the premise is pretty great, it's just the opposite of easy to find a coherent example

```  
@version:3.38
@include "scl.conf"

# this is a comment :)

options {flush_lines (0); keep_hostname (yes);};
source s_sys { system(); internal();};
destination d_mesg { file("/var/log/messages"); };
filter f_default { level(info..emerg) and not (facility(mail)); };

log { source(s_sys); filter(f_default); destination(d_mesg); };)
```

# Rsyslog format

## References

[rsyslog.com](https://www.rsyslog.com/doc/configuration/examples.html)  

And now with rsyslog, we are back to something manageable. There are also more complex things like templates that can be added but that is beyond the scope of this discussion.

```
*.info @server.example.net;RFC3164fmt
*.warn /var/log/message
```

# Appliances that Need Personalized Attention

## References

[Configuring Cisco allpiances](https://www.cisco.com/c/en/us/td/docs/switches/metro/me1200/controller/guide/b_nid_controller_book/b_nid_controller_book_chapter_010101.pdf)  

OPNSense and Cisco are the only appliances I have that need anything specific in their 
configurations. OPNSense needs an IP address rather than a hostname to keep it from getting confused and
reaching to the wrong network or interface to find the syslog server. And Cisco is its very own brand 
of problem which eveyone is probably used to already! For maximum ---- it is best to use a static 
IP on the Graylog server, but also ensure that the DNS server has all appropriate A, AAAA, CNAME, and PTR
records. Manual entries are acceptible, but automatic entries are probably more reliable.

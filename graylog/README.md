# Graylog
*Log analyzer and SEIM rolled into one*

The basic use case for Graylog is ingesting logs from various appliances and processing them into a more understandable format for people. While this functionality is pretty game-changing in and of itself, this would only scratch the surface of what Graylog is capable of. Let's summarize with a mash-up of technobabble and real life applicability.

Graylog can recognize most types of logs, and also is capable of custom input processing. This means that you can send just about anything you want to Graylog, and still make sense of it. The inputs can be aimed at a custom port, pushed into a stream, processed, indexed into a database, filtered, enriched using external services, then finally displayed for human edification.

In practice, this becomes extremely simple. For example, viewing logs from my Suricata instance often shows DNS queries to TLD's that are considered risky or hostile:
- `Query for .to TLD`
- `Query for .cc TLD`
- `Query for .pw TLD`

If you were to search any of these TLD's, you would quickly learn that the registrars that usually handle these TLD's are extremely lackadaisical about the veracity of their customers' identies and intentions. This has lead to a proliferation of malware hosts coming out of these registries. So really not good. But also, these logs are completely unhelpful! This is where Graylog makes things extremely simple. In my deployment, Suricata sends logs to its own port. Bind also has its own port. This make things rather simple- all I have to do to find particulars for the DNS query is to search the Bind9 input stream. This stream contains the requesting machine, the hostname requested, and the results of the lookup.

Additionally, log enrichment can be performed which can add things like geolocation, reputation (i.e. liklihood of malicious activity), Mitre ATT&CK tactic recognization, VirusTotal and other malware database lookups.

Let's not get caught up in the single track, wide as it may be, of a security incident tool. Graylog can also be used to troubleshoot configuration issues. As I mentioned earlier, pretty much any log can be processed. I personally use Graylog as a troubleshooter quite often. For example, say you are working inside an AD environment where computers are often shared, and also personal devices are connected to some services. Let's also say that one of the users is having their account locked out randomly and unpredictably. Of course, you can log on to the domain server and check for `Event ID 4625`, then try to match the failed login to the correct username. But what if you have more than one AD login server at a site? And what if you have more than one site? The slog through event viewers can become pretty cumbersome. You can try to be a little lazy and load events remotely rather than log on to each server, but that can introduce enormous delays in log loading. *Or* you can configure all these servers to send their logs to a central location. Once these logs have been centralized, catalogged, enriched, and collated, checking where and when the incorrect logins originated from becomes rather trivial.


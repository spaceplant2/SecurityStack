# MISP
**Threat data enrichment**

MISP is a distributed database that facilitates sharing threat information. There are many similar systems in existence, and there is often overlap. The best security ecosystems will include data of several different types, and from as many different sources as possible. For example, it is well known that using a multi-source lookup service will yeild different results than the individual data service yeilded on its singular lookup service.

The reason to focus on MISP here is because is does pull an enormous ammount of threat data that can be cross referenced and inserted into your own events. This data gets referenced and correlated to other internal data to expand the knowledge as well as reduce noise. It will be added to each singular matching event in the form of a new key and value pair that is controled by the requesting source, and thus already natralized in the collection.

Data enrichment provides telemetry and meta data surrounding your events. For example, lets say our data is showing an couple events that look like login to Microsoft's Azure services. This would be completely normal at almost any business and far from a surprise at a personal residence. Our date would be passed to MISP, however, and there would be some additions into the records that would pain a whole different story. You see, this specific login event was sent from a router, operating on port 7777. This would match data in MISP related to [Quad7](https://www.team-cymru.com/post/botnet-7777-are-you-betting-on-a-compromised-router) which is a home router based botnet built and controlled by the Chinese government and dedicated to deistributed password bruteforcing.

There are a lot of other moving pieces to this story that MISP does *not* handle, but a properly built security stack will see this event and correlate other events to build a picture of what is actually happening. The key here is the telemetry and conglomerated data that MISP has provided. In the case of Quad7 being discovered by our stack, MISP mould be consulted many times for seemingly unrelated events and each time would provide the keys that tied them all together.


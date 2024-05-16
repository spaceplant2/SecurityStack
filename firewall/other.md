# If You Don't Like my Choice....

*I might have mentioned that my opinion isn't the only good one?*

So if you don't like OPNSense for any reason, here are some choices that will work just as well in this scenario:

- [IPFire](https://www.ipfire.org/)
  - The first pre-packaged firewall I used. While I really like the philosophy and the interface, it is lacking in modern features. Still much better than the highly-touted solution packaged on any consumer-grade router.
- [Sophos](https://www.sophos.com/en-us/products/next-gen-firewall)
  - Still free, and really really astronomically easier to get started with. But under the hood, this is just PFSense rebuilt on a linux kernel and with a really pretty GUI. I have two minor gripes: keeping up with kernel updates is sometimes lacking, and Sophos refused to include a Crowdsec plugin in favor of their own effort.
- [PFSense](https://www.pfsense.org/)
  - The slightly more commecrial version of OPNSense. OPNSense is a fork of PFSense, so ¯\_(ツ)_/¯
- [Endian](https://www.endian.com/community/)
  - I don't have hands-on experience with this, but it seems on the surface to be another Linux-based reboot of PFSense. My assesment: seems that this is for advanced users to hone their skills.
- [VyOS](https://vyos.io/)
  - This is really the tool of choice for those who know *exactly* what they are doing. The advantage is also the disadvantage - if you know what you are doing, this is actually unparalleled.
- [Untangle](https://www5.untangle.com/Untangle-Unified-Threat-Management-Solution)
  - Now we are moving into the realm of paid services. Untangle is as quality as the preceeding entries. It's downfall is that it requires purchase.

The last entry is going to have to be a group - **enterprise-class firewalls**. Let me be clear: these products are top-notch! They are also expensive. Since this repo is aimed at building an affordable learning experience, I will sum these all up with this: if you have the money, try these out! At the very least, having this experience may well be beneficial for your career.

[Back to Main](../README.md)

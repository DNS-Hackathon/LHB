# getBETTERinfo -- Making getaddrinfo() better

## Background

The **getaddrinfo()** API has well-known [limitations][]. In the
[DApper][] project at the 2023 DNS Hackathon, a "solution" was
sketched out, which identified a preferred resolver library for use
when building any chosen application. Discussion of this proposal with
the lead developers of a widely-used application library, supported on
multiple platforms, evoked strong push-back, due to concerns including:

- insufficiant availability of the chosen resolver library on the
  range of platforms supported by the application library;
- the degree to which integrating an unfamiliar resolver library might
  distract from other work to support and develop the application
  library;
- doubt over the availablity of the resources of the developers
  of the chosen resolver library for ongoing maintenance.

## Proposed Hackathon Project

Goal: design data structure and related APIs for making HTTPS/SVCB
data, as well as what getaddrinfo() provides, available, as simply as
possible, to an application.

Things to take into account (first three are already handled by getaddrinfo):

- [RFC3493][] (addrinfo)
- [RFC3484][] (address selection policy -- ip6addrctl.conf (BSD), gai.conf(GNU))
- [nsswitch][]
- application pragmatics
- [RFC9460][] (HTTPS/SVCB RRs)
- [Happy Eyeballs v3 draft][]

## Resources

- [RFC3484][]: "Default Address Selection for Internet Protocol version 6 (IPv6)"

- [RFC3493][]: "Basic Socket Interface Extensions for IPv6"

- [RFC9460][]: "Service Binding and Parameter Specification via the DNS (SVCB and HTTPS Resource Records)"

- [Happy Eyeballs v3 draft][]: "Happy Eyeballs Version 3: Better Connectivity Using Concurrency"

- [nsswitch][]: "System Databases and Name Service Switch (from GNU libc manual)"

- [limitations][] of getaddrinfo: "getaddrinfo sucks. everything else
  is much worse (blog post covering material presented at FOSDEM 2025,
  Brussels)"

- [DApper][]: "Output from DApper project at 2023 DNS Hackathon, Rotterdam"

---

[RFC3484]:
https://www.rfc-editor.org/rfc/rfc3484.html
"Default Address Selection for Internet Protocol version 6 (IPv6)"

[RFC3493]:
https://www.rfc-editor.org/rfc/rfc3493.html
"Basic Socket Interface Extensions for IPv6"

[RFC9460]:
https://www.rfc-editor.org/rfc/rfc9460.html
"Service Binding and Parameter Specification via the DNS (SVCB and HTTPS Resource Records)"

[Happy Eyeballs v3 draft]: 
https://datatracker.ietf.org/doc/html/draft-pauly-v6ops-happy-eyeballs-v3-02
"Happy Eyeballs Version 3: Better Connectivity Using Concurrency"

[nsswitch]:
https://www.gnu.org/software/libc/manual/html_node/Name-Service-Switch.html
"System Databases and Name Service Switch (from GNU libc manual)"

[limitations]:
https://valentin.gosu.se/blog/2025/02/getaddrinfo-sucks-everything-else-is-much-worse
"getaddrinfo sucks. everything else is much worse (blog post covering material presented at FOSDEM 2025, Brussels)"

[DApper]:
https://github.com/DNS-Hackathon-2023/DApper
"Output from DApper project at 2023 DNS Hackathon, Rotterdam"

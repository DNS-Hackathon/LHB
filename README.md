# LHB -- Lookup Hostname Best-practice

## Background

The DNS has always been used to do more than address resolution for a
given hostname.  For example, the MX record type was defined in the very
beginning in [RFC1035][] (November 1987).

Since than, the variety of record types defined to announce service-specific
data has never stopped growing.  Despite this, many applications, or the
libraries on which they are based, have continued to rely on the
gettaddrinfo() API as their main, or only, means of accessing the DNS.

## Proposed Hackathon Projects

Two projects were proposed, which came to be merged at the beginning of the
Hackathon

- Ali: anonymous project motivated by obstacles encountered in
  developing the LadyBird browser engine;
  
- Niall: [getBETTERinfo][] project aimed at "Making getaddrinfo() better", either
  by specifying extensions to the API and underlying data structure, or by
  "wrapping" this structure in a richer one which would also accommodate
  relevant DNS data.
  
## See also

- [Roadmap][]
- [Progress][]

## TODO

- Add description of Ali's proposed project
- Add POC code from Ali and Asbjørn
- Add gap analysis showing application requirements not met by getaddrinfo()

## Etymology

The project title is a backronym from "LHB", an abbreviation of the Dutch
word "LieveHeerBeestje", which means "Ladybird" (American: "LadyBug"),
and refers to the project which motivated Ali's proposal.


---

[RFC1035]:
https://www.rfc-editor.org/rfc/rfc1035
"DOMAIN NAMES - IMPLEMENTATION AND SPECIFICATION"

[getBETTERinfo]:
https:getBETTERinfo.md
"proposed project: getBETTERinfo -- Making getaddrinfo() better"

[Roadmap]:
https:RoadMap.md

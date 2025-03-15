# DNS Hackathon 2025 -- LHB Project

## Project Background

During the team-forming stage of the Hackathon, it became clear that
there was strong overlap between Ali's proposal and Niall's, and also
that Ali's had a scope that was narrow enough that concrete near-term
results could be expected.

A team formed around a merged project, including Asbjørn, Bjørn, and
Teddy, as well as Ali and Niall.

## Road Map

This road map was prepared as pre-event homework for the getBETTERinfo
project proposal. After an animated initial discussion, perhaps well
described by the old cliché "violent agreement", we realized we had
actually addressed most of the items, so decided to keep the road map
as it stood.

1. Share perceptions about what needs to be done to to "improve"
   **struct addrinfo** and **getaddrinfo()**.

2. Identify DNS data needed in addition what current **struct
   addrinfo** can carry.

3. Identify options for the way ahead:

	- Extension to **struct addrinfo** (additional flags, fields);
	- Wrapping **struct addrinfo** in an outer struct (as currently in
      **libcurl**);
	- Something else.

4. Identify obstacles posed by existing implementations.

5. Develop specification for new (wrapping, extension, whatever) data
   structure.
   
6. Identify implementation options:
	- fork of selected existing implementation;
	- shim library to provide wrapping;
	- something else.

7. Consider how, and to whom, to promote solution.

8. Possibly start on prototype code.

## Progress (day 1)

A lively and enjoyable discussion took place, with useful contributions
from all team members.

Ali, Asbjørn, and Niall proposed to produce code and documentation for
review on day 2, based on this discussion. Bjørn and Teddy proposed
not to contribute artefacts, so as to be free of "author bias" for
this review.

Details are recorded below, where the numbering below matches corresponding
items in the road map above.

1. What needs to be done

	- Complement address data available from getaddrinfo() with
	  application- or operation- specific DNS data as, for example,
	  from MX, TLSA, or HTTPS records.
	  
	- Do this by wrapping an outer data structure around addrinfo
	  (rather than by extending addrinfo itself) and in a way which
	  can eventually accommodate a variety of record types, as need
	  for support arises appears.
	
	- Allow propagation of other DNS response data besides the records
	  carried in the ANSWER section, including at least header data,
	  extended error codes, and additional records.
	  
	It was noted that libcurl (which is a component of current work
    for Ali and Niall), when built with support for the HTTPS RR,
    includes wrapping of the kind considered in the definition of
    `struct Curl_dns_entry`, but with restriction to the HTTPS record
    type, and apparently to a singleton HTTPS RRset.

2. Additional DNS data needed

	- Scope is to include "whatever is significant", with the detailed
	  definition of this phrase to developed as the project proceeds
	  during the Hackathon, and in eventual follow-up work.
	  
	- In order not to lose any of "whatever is significant", a
	  prudent initial definition of this should include:
	  * (a copy of)
	    the entire wire-format response buffer for each DNS query made;
	  * a "next item" pointer, so that (in case successive DNS queries
	    are needed) the significant material from each DNS query can be
		dealt with separately;
		and
	  * additional fields (views) representing the results of parsing,
	    sorting, and analyzing the response.
	  
3. Identify options for the way ahead:

   The project team selected wrapping as the most promising option for
   the way ahead.

4. Identify obstacles posed by existing implementations.

   The project team preferred to attempt proof-of-concept code to
   address specific requirements, rather than to spend time on
   cataloguing obstacles.
   
   In particular:

   - Ali proposed to work on POC code, based on libcurl, which would
     interpret a hand-crafted data structure of the kind described in
     item 2 above;

   - Asbjørn proposed to work on complementary POC code, which would
     populate such a data structure by querying the DNS using c-ares;

   - Asbjørn also proposed to develop a gap analysis, informed by
     results from his POC code, showing what DNS data are needed for
     current application purposes, bu unavailable from getaddrinfo().

5. Develop specification for new data structure

   This is to be informed by experience from the POC code artefacts
   mentioned in item 4 above.

6. Identify implementation options

   This is to be informed by experience from the POC code artefacts
   mentioned in item 4 above.

7. Consider how, and to whom, to promote solution.

   This is to be informed by experience from the POC code artefacts
   mentioned in item 4 above.

8. Prototype code
   
   Ali and Asbjørn started work on the items mentioned in item 4 above
   and expect to report progress on day 2.
   
9. Other effort

   - Niall proposed to write draft notes of the first day's work, for review
     on day 2.

This concludes the DRAFT record of the first day's work on the LHB project.

---

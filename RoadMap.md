# Road Map for proposed getBETTERinfo project

If a Hackathon team gathers around this project proposal,
it will likely give attention to the following.

1. Share perceptions about what needs to be done to to "improve"
   **struct addrinfo** and **getaddrinfo()**.

2. Identify DNS data needed in addition what current **struct
   addrinfo** can carry.

3. Identify options for the way ahead:

	- Extension to **struct addrinfo** (additional flags, fields);
	- Wrapping **struct addrinfo** in an outer struct (as currently in
      **libcurl**);
	- Something else.

4. Identify obstacles posed by existing impementations.

5. Develop specification for new (wrapping, extension, whatever) data
   structure.
   
6. Identify implementation options:
	- fork of selected existing implementation;
	- shim library to provide wrapping;
	- something else.

7. Consider how, and to whom, to promote solution.

8. Possibly start on prototype code.

---

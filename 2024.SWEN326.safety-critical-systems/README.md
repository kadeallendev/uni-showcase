# SWEN326: Safety-Critical Systems

This course addresses the concepts, techniques and tools required for developing computer systems that are applicable where safety and reliability is paramount. Topics include: the concepts and principles underlying safety-critical systems & standards (e.g. DO178C and IEC61508); techniques for design validation (e.g. model checking); and implementation techniques for ensuring software correctness (e.g. coding guidelines, testing, static analysis, etc). Practical work will involve the design, implementation, and analysis of simple safety critical applications (e.g. for industrial, embedded and healthcare systems).

## Course learning objectives

Students who pass this course should be able to:

1. Describe the key principles of safety critical systems and the implications of these for software design and implementation.
2. Select and apply appropriate standards and processes to develop safety critical systems, for example IEC 61508 and DO-178C.
3. Analyse potential risks, hazards, threats, and failure modes in the designs of safety critical systems.
4. Design and construct software following safety critical standards, processes, and design techniques.
5. Evaluate system designs and software against safety critical standards.

## Assignments

There was only one assignment for this course which was a group project.

This was a group project in which we had to develop an autopilot system, along with a simulator and graphical client. The autopilot system had to comply with the DO178-C software standards.

I was responsible for developing the simulator and autopilot system, using Java to do so. The two systems communicated via a WebSocket connection.

The simulator system would send sensor values (a rudimentary aircraft simulation) over the connection to the autopilot system. These values were sent asynchronously at different intervals.

The autopilot system would receive these values, process them (to ensure they are reliable and accurate readings), and relay them to the client system.

The simulator could be controlled from the autopilot system via sending commands such as 'begin' and 'shutdown'.

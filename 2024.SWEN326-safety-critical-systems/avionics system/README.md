# Avionics System

This was a group project in which we had to develop an autopilot system, along with a simulator and graphical client. The autopilot system had to comply with the DO178-C software standards.

I was responsible for developing the simulator and autopilot system, using Java to do so. The two systems communicated via a WebSocket connection.

The simulator system would send sensor values (a rudimentary aircraft simulation) over the connection to the autopilot system. These values were sent asynchronously at different intervals.

The autopilot system would receive these values, process them (to ensure they are reliable and accurate readings), and relay them to the client system.

The simulator could be controlled from the autopilot system via sending commands such as 'begin' and 'shutdown'.

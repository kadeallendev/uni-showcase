# COMP307 A4: Scheduling and Routing

This assignment involved two parts.

# Part 1: Scheduling

The first part involved solving a typical job shop scheduling problem. The problem consisted of three jobs and two machines. I was tasked with using both the first-come-first-serve heuristic and the shortest processing time heuristic to calculate the finishing times and makespans of the schedules.
Additionally, I had to compare the efficiency of these rules in a given context.

# Part 2: Routing

This part involved creating a program that would implement both the nearest-neighbour and savings cost heuristics to find a solution to a vehicle routing problem.
The nearest-neighbour heuristic essentially looks for the next closest node within the current route's capacity constraints, returning to the depot if no nodes are available.
The savings cost heuristic involves computing a list of costs associated with merging every pair of routes. The merge with the maximum saving would be selected and merged if it's demand did not exceed the capacity constraint.

# Q-Learning

# Reinforcement Learning
Let's describe the "taxi problem". We want to build a self-driving taxi that can pick up passengers at one of a set of fixed locations, drop them off at another location, and get there in the quickest amount of time while avoiding obstacles.

# Building pipeline to address Problem

Let's break down what we're seeing here:

R, G, B, and Y are pickup or dropoff locations.
The BLUE letter indicates where we need to pick someone up from.
The MAGENTA letter indicates where that passenger wants to go to.
The solid lines represent walls that the taxi cannot cross.
The filled rectangle represents the taxi itself - it's yellow when empty, and green when carrying a passenger.
Our little world here, which we've called "streets", is a 5x5 grid. The state of this world at any time can be defined by:

Where the taxi is (one of 5x5 = 25 locations)
What the current destination is (4 possibilities)
Where the passenger is (5 possibilities: at one of the destinations, or inside the taxi)
So there are a total of 25 x 4 x 5 = 500 possible states that describe our world.

For each state, there are six possible actions:


Move South, East, North, or West
Pickup a passenger
Drop off a passenger
Q-Learning will take place using the following rewards and penalties at each state:

A successfull drop-off yields +20 points
Every time step taken while driving a passenger yields a -1 point penalty
Picking up or dropping off at an illegal location yields a -10 point penalty
Moving across a wall just isn't allowed at all.

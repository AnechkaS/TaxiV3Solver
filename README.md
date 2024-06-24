Description:
The Taxi-v3 environment involves navigating a taxi in a 5x5 grid to pick up and drop off passengers at designated locations (Red, Green, Yellow, Blue). The goal is to move the taxi to the passenger’s location, pick up the passenger, navigate to the desired destination, and drop off the passenger.

Action Space:

Discrete(6)
0: Move south
1: Move north
2: Move east
3: Move west
4: Pickup passenger
5: Drop off passenger
Observation Space:

Discrete(500)
25 taxi positions
5 passenger locations (including in the taxi)
4 destination locations
Rewards:

-1 per step unless another reward is triggered
+20 for delivering the passenger
-10 for illegal pickup/drop-off actions
Noops incur the time step penalty
Map:
+---------+
|R: | : :G|
| : | : : |
| : : : : |
| | : | : |
|Y| : |B: |
+---------+
Starting State:

The episode starts with the player in a random state.
Episode End:

Termination: The taxi drops off the passenger.
Truncation: The length of the episode reaches 200 steps.
Additional Information:

Transition probability (p) is always 1.0.
The action mask (info["action_mask"]) indicates if actions will change the state.

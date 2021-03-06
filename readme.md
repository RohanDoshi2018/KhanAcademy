INFECTION
=========

####Author: Rohan Doshi
####Project: Infection

####Overview
In javascript, I implemented total_infection and limited_infection. I 
also created a  web app for visualizing and dynamically manipulating the 
graph. A demo can be found at: 
http://rodoweb.com/KA/Infection.html

The code can be found on Github:
https://github.com/RohanDoshi2018/KhanAcademy

####Solution

In my solution, I created a undirected graph. I chose to model this as an 
undirected as opposed to a directed graph because infections are transitive 
(mentors can infect students, and students can infect mentors). To keep 
track of the rollout of different versions of KA, each node has a "version" 
attribute, which cooresponds to a color in the visualization. As for 
coaching relations, each node is randomly assigned a size uniformly between 
0 and 1. Bigger nodes are mentors to smaller neighboring nodes.

To implement total_infection, I conducted a depth-first-search starting 
on a clicked node to access the entire connected component (e.g. a classroom).
Every visited node would become "infected" and change color, depending on 
the software version of KA selected in the settings section.

To implement limited_infection, I iterated through all the nodes, conducting
depth-first-search from each node to count how many potential people can 
be infected starting from that specific person (e.g. number of elements
in a particular connected component). If a node is in a connected component
with the correct number of nodes, the specified node would be infected. If 
no node meets this criteria, the end user will be notified in the settings
panel.

####Future Development
If I had more time:
* I would have optimized the data structures for faster node searching
(e.g. hash tables). 
* I would have significantly improved the UI/UX visualization.
* I would have built in a window pane to visualize data about specific nodes.
* I would allow for the dynamic creation of nodes with clicks on the screen,
   and build in the functionality to drag nodes as well.

####Credit
The sigma.js library was used to help in the plotting of node and edge objects.
# Master Mobility

This repository contains some Jupyter Notebooks to read, process and study pedestrian mobility GPS trajectories, collected using the Wikiloc app. (https://www.wikiloc.com/) and exported in GPX files. 

The code is adapted to a particular experimental case, in which 18 groups of 3-6 people from "Barri Primer de Maig (Granollers, Spain)" participated by walking through the neighborhood while exploring and choosing particular places to peform a list of actions. They brough an IPAD tablet device with the Wikiloc open and recording the trajectory. 

- The folder "original data" contains the raw collected data, i.e., 18 gpx files with the trajectories of the different groups.
- The folder "processed data" contains the filtered and processed data in csv format (i.e., 18 csv files). 
  
 - The original data have gone through the following filtering and processing process: 
  1. First, each individual trajectory is projected on a map of the neighbourhood, and the noisy records that may appear (specially at the beginning and the end of the trajectory) are removed from the data-set.
  2. Some basic calculations are performed and added as new columns in the data-frame:  The time difference (s), the distance (m) and the velocity (m/s) between consecutive GPS records. Also the orientation angle between each vector connecting two GPS points and the North, and the change in the orientation. Finally, each GPS record is considered as a "stop" if the time difference between the current GPS record and the next one is greater or equal than 10s (since the Wikilop app. stops recording GPS records when it is not detecting movement).  

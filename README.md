# Master Mobility

This repository contains some Jupyter Notebooks to read, process and study pedestrian mobility GPS trajectories, collected using the Wikiloc app. (https://www.wikiloc.com/) and exported in GPX files. 

The code is adapted to a particular experimental case, in which 18 groups of 3-6 people from "Barri Primer de Maig (Granollers, Spain)" participated by walking through the neighborhood while exploring and choosing particular places to peform a list of actions. They brough an IPAD tablet device with the Wikiloc open and recording the trajectory. 

- The folder "original data" contains the raw collected data, i.e., 18 gpx files with the trajectories of the different groups.
- The folder "processed data" contains the filtered and processed data in csv format (i.e., 18 csv files). 
  
 - Data_processing.ipynb: The original data have gone through a simple filtering process in which each individual trajectory is projected on a map of the neighbourhood, and the noisy records that may appear (specially at the beginning and the end of the trajectory) are removed from the data-set. The data is further processed and new columns are added corresponding to the time difference (s), distance (m), velocity (m/s), orientation respect to the North and re-orientation between consecutive GPS records. Each GPS record is also labelled as "stop" or "moving". We consider a GPS point as stopped if the time difference between the current GPS record and the next one is greater or equal than 10s (since the Wikilop app. stops recording GPS records when it is not detecting movement).  

- Basic_statistics.ipynb: In this Notebook some basic statistics are obtained for the individual trajectories and also averages over all trajectories are performed. Trip duration, distance covered, effective speed, radius of gyration, tortuosity, number of stops, etc... The probability density function (normalized histogram) of some of the variables is also obtained. 

- Mobility_characterisation.ipynb: A more advanced study is carried out in order to characterize the pedestrian mobility. We obtain the mean squared displacement, the auto-correlation of the velocities, etc.

- Stops.ipynb: The stops made during the experiment are also studied. We detect the stops and their duration and project them on maps.



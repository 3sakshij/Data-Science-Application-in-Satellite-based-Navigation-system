# Data-Science-Application-in-Satellite-based-Navigation-system
As a Data Science Intern at IIT Indore I worked on the GNSS/GPS and NavIC Data . Build the pipeline to extract, clean and plot the large satellite data .

Download Requirements : 
pip install 
pandas
numpy
ismrpy
bokeh
pandas-bokeh
datetime
julian
tkinter

Run the Final website.py script to see the website.
# Introduction

The Ionosphere is part of Earth’s upper atmosphere, between 80 and about 600 km where Extreme
Ultraviolet (EUV) and x-ray solar radiation ionizes the atoms and molecules thus creating a layer of
electrons. the ionosphere is important because it reflects and modifies radio waves used for
communication and navigation. Other phenomena such as energetic charged particles and cosmic
rays also have an ionizing effect and can contribute to the ionosphere. The atmospheric atoms and
molecules are impacted by the high energy the EUV and X-ray photons from the sun. The amount
of energy (photon flux) at EUV and x-ray wavelengths varies by nearly a factor of ten over the 11-
year solar cycle. The density of the ionosphere changes accordingly. Due to spectral variability of
the solar radiation and the density of various constituents in the atmosphere, layers are created within
the ionosphere, called the D, E, and F-layers. Other solar phenomena, such as flares, and changes in
the solar wind and geomagnetic storms also affect the charging of the ionosphere. Since the largest
amount of ionization is caused by solar irradiance, the night-side of the earth, and the pole pointed
away from the sun (depending on the season) have much less ionization than the dayside of the
earth, and the pole pointing towards the sun. The charged plasma of the ionosphere bends the path
of the satellite radio signal, due to increased TEC there is an inaccuracy in position based on the
satellites overhead. So it is important to study data and how it's affecting the Navigation System. A
satellite navigation or satnav system is a system that uses satellites to provide autonomous geospatial positioning. It allows small electronic receivers to determine their location (longitude,
latitude, and altitude/elevation) to high precision (within a few centimeters to meters) using time
signals transmitted along a line of sight by radio from satellites. The system can be used for
providing position, navigation or for tracking the position of something fitted with a receiver
(satellite tracking).A satellite navigation system with global coverage may be termed a global
navigation satellite system (GNSS). Current work involves the use of raw data collected from the
receivers stationed at IIT Indore for both GNSS and NavIC.

My work involves the pre and post
processing of these data from the raw data files to generate the user friendly Plots and interface for
the website. This post processed data can further be used in various Space Weather and Navigation
applications.

# Objectives
1. To read the raw data using optimized library functions
2. Apply a filter technique where in the post processed data is free from bad data (i.e.,
erroneous values)
3. Further step to analyze the data to generate various plots.
4. Concatenating larger files to simplify the post processing.
5. Categorizing the data based on the Column value to perform mathematical validations.
6. Updating the day-to-day plots over the website.

# Algorithm Followed for generating Plots for the GNSS are as follows:

## Flowchart 
![flowchart](https://user-images.githubusercontent.com/39564683/156942087-76042dc4-f3c3-48a7-9992-0af3809e1654.PNG)

Step 1 : Reading and Understanding the data
PolarRx5S Receiver collected the data in ismr format as stated in above chapter .An algorithm based
program should be customized to read the .ismr files that are being generated by the GNSS receiver.
Many sorting techniques have been used to match the criteria and eliminate bad data . Before
processing data further it is always better to use the data in the right and efficient format to process
it further . So that is the reason Library named Ismrpy is used which converts the data into proper
strategized format and hence easily understood.

Step 2 : Checking the Contents of files
After reading and understanding data ,Availability of all the files for every Hour , day, month and
a year need to be checked. As Ismrpy reads the file in the data frame like pandas , Small python
script can check for the availability of all the files and prompt the name of the file if found missing
and concatenate the remaining files.

Step 3 : Categorizing data of GNSS for Different Constellations
To Categorize data according to the constellation SVID column is used . Values of the different
SVID values for different constellations has been specified in the manual of PolarRx5S Receiver

Step 4 : Eliminating the bad data
There are the nan values in the form string where data is not available so the nan string is converted
into integer and replaced with the 0 values .

Step 5 : Conversion of the Universal Time to Local Time and Julian Time
Separate algorithm is built for the conversion of UT to Julian time 

Step 6 : Setting Elevation cutoff and Calculations of VTEC
Values of Vertical Total Electron content VTEC (is the total number of electron density in a vertical
path, also expressed in TECU (1 TECU = 1016 electrons/m2)) are calculated with STEC (Slant Total
Electron content)
Slant total electron content (STEC) is the amount of electron density along a slant path between a
satellite and a receiver, expressed in TECU (1 TECU = 1016 electrons/m2
).
Slant TEC can be computed from the integral path of the Ne is Electron density (electrons/m3
), i.e

Mapping Function for Conversion of VTEC to STEC:

![1](https://user-images.githubusercontent.com/39564683/156941865-8c0e84fe-e1fa-4f78-83d4-fc292bde71d4.PNG)



Re is the radius of the Earth (6371 km)
hI denotes the altitude of the thin shell model of the ionosphere (350 km)
E is the elevation angle of the space vehicle.

Step 7 : Generating the plots

![website](https://user-images.githubusercontent.com/39564683/156942170-9779d050-8387-4ae7-af30-4dbae5f85dac.JPG)


![scatter polot](https://user-images.githubusercontent.com/39564683/156942219-ea3fb680-5e5c-42a0-ae9e-3b3b73edb2d1.JPG)



Any queries related to code e-mail me at : Sakshijcom@gmail.com

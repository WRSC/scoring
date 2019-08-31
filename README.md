# WRSC scoring

These scripts score the performance of boats attempting challenges in the
World Robotic Sailing Competition.

A scoring script reads the GPS coordinates of the boats path, obtained from
a tracker unit, and compares them with the coordinates defining the challenge.
The rules define what to check for each challenge.

- [2019 rules](https://github.com/WRSC/rules/releases/download/wrsc2019/rule2019.pdf)
  and [rules source repository](https://github.com/WRSC/rules)
- [2019 GPS coordinates](https://github.com/WRSC/coordinates2019) (coordinates and attempts)
- [Competition tracking system](https://github.com/WRSC/tracking)

The scripts work somewhat differently, according to the demands of scoring
each challenge.

- `analyse_fleet_race`: takes a single command line argument for a GPS track in
  CSV format, reports when the boat reached each of the markers in the course.
- `analyse_station_keeping`: takes multiple command line arguments of GPS
  tracks, reports the mean radius for each challenge.
- `analyse_area_scanning`: single command line argument overview csv master file.
  Reports points for each team in the same group.
- `analyse_hide_and_seek`: single command line argument takes the number of seeks. 

To reuse these scripts for another competition, you will need to modify the
coordinates defining the challenge and the
[UTM zone number](http://www.dmap.co.uk/utmworld.htm) of the competition venue.
The scripts may also need to be updated if the rules change.

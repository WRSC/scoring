# WRSC scoring

These scripts score the performance of boats attempting challenges in the
World Robotic Sailing Competition.

A scoring script reads the GPS coordinates of the boats path, obtained from
a tracker unit, and compares them with the coordinates defining the challenge.
The rules define what to check for each challenge.

- [2018 rules](https://www.roboticsailing.org/2018/wp-content/uploads/2018/08/WRSC2018_rules_v1-1.pdf)
  and [rules source repository](https://github.com/WRSC/rules)
- [2018 GPS coordinates](https://github.com/WRSC/coordinates2018) (coordinates and attempts)
- [Competition tracking system](https://github.com/WRSC/tracking)

The scripts work somewhat differently, according to the demands of scoring
each challenge.

- `analyse_fleet_race`: takes a single command line argument for a GPS track in
  CSV format, reports when the boat reached each of the markers in the course.
- `analyse_station_keeping`: takes multiple command line arguments of GPS
  tracks, reports the 95% position-keeping radius for each, according to the
  rules. This number then needs to be divided by the boat length as a manual
  step.
- `analyse_area_scanning`: single command line argument points to a 'master'
  CSV file listing the attempts made by boats within a class (e.g.
  [for micro-sailboats in 2018](https://github.com/WRSC/coordinates2018/blob/ec29ea762e0d4b4e88db21ac0a4b1a06130e5c87/area-scanning/master_micro_sailboat.csv)).
  Reports points for each attempt.

To reuse these scripts for another competition, you will need to modify the
coordinates defining the challenge and the
[UTM zone number](http://www.dmap.co.uk/utmworld.htm) of the competition venue.
The scripts may also need to be updated if the rules change.

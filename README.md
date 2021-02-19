# f1tenth_racetracks
This repository contains maps from over 20 real race tracks (mainly F1 and DTM) downscaled on 1:10 for the usage in the F1TENTH Gym and F1TENTH Simulator.


# Included race tracks
* Austin, USA (F1)
* Brands Hatch, UK (DTM)
* Budapest, Hungary (F1)
* Catalunya, Spain (F1)
* Hockenheim, Germany (F1, DTM)
* IMS Indianapolis Motor Speedway, USA (IndyCar)
* Melbourne, Australia (F1)
* Mexico City, Mexico (F1)
* Montreal, Canada (F1)
* Monza, Italy (F1)
* Moscow Raceway, Russia (DTM)
* Norisring, Germany (DTM)
* Nuerburgring, Germany (DTM)
* Oschersleben, Germany (DTM)
* Sakhir, Bahrain (F1)
* Sao Paulo, Brazil (F1)
* Sepang, Malaysia (F1)
* Shanghai, China (F1)
* Silverstone, UK (F1)
* Sochi, Russia (F1)
* Spa, Belgium (F1)
* Spielberg, Austria (F1)
* Yas Marina, Abu Dhabi (F1)
* Zandvoort, Netherlands (DTM)

# Data Source and Processing
This repository is based on the [f1 racketrack database](https://github.com/TUMFTM/racetrack-database) which includes
the racetrack information (inner bounds, outer bounds, track width) of 20 real racetracks all around the world.
The original center lines on the real racetracks were fetched as GPS points from the OpenStreetMap project (https://www.openstreetmap.org).
We applied a smoothing algorithm to the center lines. The track widths were extracted from satellite images using an
image processing algorithm. Afterwards the data was downscaled 1:10 with a fixed track width of 2,20m so it can be
used in the F1TENTH environments.

# Content and Data Format
- maps: The tracks are displayed as occupancy grid maps based on a .pgm or .png file. That maps have a correspondong .yaml file
that includes both resolution and origin of the maps. These maps can be used in both the F1TENTH Gym and the F1TENTH Simulator.
- waypoints: [x_m, y_m, w_tr_right_m, w_tr_left_m] These files contain the center line (x, y) and the track widths to the
right (w_tr_right) and left (w_tr_left). The center lines were smoothed. Therefore, they do not lie perfectly in the
middle of the track anymore.

The quality of the source data (GPS points and satellite images) varies greatly depending on the location. Accordingly,
the quality of the results varies as well. Please bear this in mind and check whether the accuracy is sufficient for the
desired application.


# Acknowledgement
The original f1 racetrack database was created by Alexander Heilmeier from the Institute of Automotive Technology at the
Technical University of Munich.

# Related open-source repositories
* Lap time simulation: https://github.com/TUMFTM/laptime-simulation
* Race simulation: https://github.com/TUMFTM/race-simulation
* Formula 1 timing database: https://github.com/TUMFTM/f1-timing-database
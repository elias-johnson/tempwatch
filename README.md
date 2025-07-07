# tempwatch
Simple script I use to display CPU temperature on my Arch system.


## Prerequisites
This script relies on the `lm_sensors` package.

1. `sudo pacman -S lm_sensors` to install the package
2. `sudo sensors-detect` to identify available sensors
3. `sensors` will now display data relating to the available sensors on your machine

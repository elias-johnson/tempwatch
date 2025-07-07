#!/bin/bash

sleep_time=0.5
total_temp=0
temp_samples=0

loop='true'
while [ "$loop" = true ]; do
  # Fetch current CPU temperature in Celsius
  current_temp=$(sensors | grep "Package id 0" | awk '{print $4}')

  # Strip junk from temperature reading
  current_temp="${current_temp#+}"
  current_temp="${current_temp%%.*}"

  # Track average temperature readings
  total_temp=$(( total_temp + current_temp ))
  (( temp_samples++ ))

  echo "$current_temp.0 C"
  sleep $sleep_time
  trap 'loop=false' SIGINT
done

# Display average temperature once finished
echo
echo
echo "Average temperature: $(awk "BEGIN {print $total_temp/$temp_samples}") C"
echo "Samples taken:       $temp_samples"
echo "Seconds elapsed:     $(awk "BEGIN {print $temp_samples*$sleep_time}")s"
echo

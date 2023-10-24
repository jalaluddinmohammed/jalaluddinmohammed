#!/bin/bash

echo "Enter the time you waste on daily in hours:"
read x

if [[ $x =~ ^[0-9]+$ ]]; then
  if [ "$x" -lt 9 ]; then
    monthly=$(($x * 30))
    days=$(echo "scale=1; $monthly / 24" | bc -l)
    yearly=$(echo "$days * 12" | bc -l)

    echo "Monthly (in hours) you waste: $monthly hours"
    echo "Monthly (days) you waste: $days days"
    echo "Yearly you waste: $yearly days"
  else
    echo "Enter the waste hours less than 6 to calculate waste timings"
  fi
else
  echo "Invalid input. Please enter a valid number of hours."
fi

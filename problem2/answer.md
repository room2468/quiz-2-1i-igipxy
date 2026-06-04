#!/bin/bash

# Read input
read total
read used

# Calculate free memory
free=$((total - used))

# Calculate usage percentage
usage=$((used * 100 / total))

# Determine status
if [ $usage -le 50 ]; then
    status="Normal"
elif [ $usage -le 90 ]; then
    status="Warning"
else
    status="Critical"
fi

# Output results
echo "Free: $free MB"
echo "Usage: $usage%"
echo "Status: $status"

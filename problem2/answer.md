#!/bin/bash

read -r total
read -r used

free=$(( total - used ))
usage=$(( used * 100 / total ))

if (( usage >= 90 )); then
    status="Critical"
elif (( usage >= 70 )); then
    status="Warning"
else
    status="Normal"
fi

echo "Free: $free MB"
echo "Usage: $usage%"
echo "Status: $status"

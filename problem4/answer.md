#!/bin/bash

total=0
highest_size=0
highest_user=""
over_1000=0

while IFS= read -r line; do
    read -r username size <<< "$line"
    
    (( total += size ))
    
    if (( size > highest_size )); then
        highest_size=$size
        highest_user=$username
    fi
    
    if (( size > 1000 )); then
        (( over_1000++ ))
    fi
done

echo "Total usage: $total MB"
echo "Highest user: $highest_user ($highest_size MB)"
echo "Users over 1000 MB: $over_1000"

#!/bin/bash

read -r first last

# Last name in ALL CAPS, first name in Title Case
echo "${last^^}, ${first^}"

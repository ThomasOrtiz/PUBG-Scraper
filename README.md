## Description
I wanted an easy way to get my friends ratings in PUBG. This command-line program uses 
[https://pubg.op.gg/](https://pubg.op.gg/) as a means of obtaining a person's stats.

In order to obtain a person's stats we require an `id` to access pubg.op.gg api. However,
I couldn't be bothered to go through and find all of my friend's `id`'s and decided to make a webscraper instead.

Heres how the program functions:
1. Grab pubg usernames from `input.json`.
2. Grab the cached `username to id` mapping from `id-mapping.json` if it exists.
3. Start aggregating data by iterating through username array:
    - If the username doesn't have an `id mapping` then webscrape from pubg.op.gg by using phantomJS.
    - If the username DOES have an `id mapping` then call pubg.op.gg's api directly (this saves a lot of time)
4. Update the cached data so future runs are quicker.


## Pre req
1. Install [node](https://nodejs.org/en/).

## Installation
1. Clone the repo
2. `npm install`

## Running
1. Add pubg character names to `input.json`. 
2. `node phantom-server.js`

## Output
1. Open output.json
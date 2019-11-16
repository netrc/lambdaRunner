# lambdaRunner

Put together a fun visualization of cloud lambda systems chatting with each other

E.g. AWS lambda calls (randomly) Google Cloud Functions, which calls Azure, which calls CloudFoundry

latencies, other data stored to database and visualized

# TODO

* each lambda will call the other lambdas randomly
* need to define some sort of 'cron' lambda to kick off the cascade process at regular-ish intervals
  * e.g. once every 15 seconds, call one of the lambdas, giving other lambda addresses
* the receiving lambda stores the latency, other data, and (?) randomly calls another lambda in the list, deleting that lambda from list
* Issue: Don't create an infinite firestorm of requests
* Issue: Stop denial of service attacks; only the 'cron' lambda should be able to kick off the cascade process. (hidden internal key?). 
* Constraint: Free tiers of lambdas and database

* Visualization:  Circle of nodes for each lambda; node glows when it receives (stores) data. 
  * show sparkline or some graph for each node latency?
  * show some general graph of all latencies
* Firebase for db?  So visualizer can get 'live' updates

* Install lambdas in different cloud regions too....  How many is too many?  10/25/100 lambdaRunner nodes?


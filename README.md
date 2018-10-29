# Coding Challenge - Data Engineer

This repository was created to host the helper files for the Data Engineering role challenge.

The instructions below imply you have a minimum knowledge on how to run a docker container. This does not imply your \
solution too should run in Docker. 
You are free to write your solution in the language of your preference within a short list we provide. However, we recommend\
you choose a language that you judge is the most appropriate for this kind of problem, taking into account easyness and time\
to develop, performance, and availability of libraries and connectors that might be helpful.

The languages you can consider as candidates for most appropriate ate:
* JavaScript
* Golang
* Python
* Scala

## The problem - Calculating real-time traffic in a bus network

There is a bus network with a few routes. Each route is formed by a fixed sequence of stops. In each route, a few vehicles run - they might sometimes change routes after finishing a route.

The mayor has implemented a system in which buses have a GPS, and they send their coordinates every 30 seconds or so. Sometimes less, sometimes more, but never more than 120 seconds. With those coordinates, a central server issues forecasts of the arrival time of those vehicles to each of the following stops in its route.

There is a server that provides those forecasts. They come in a big JSON, with all forecasts calculated in a window of 30 seconds.

There is one problem: the forecasts provided don't take traffic into account. Therefore they are good, but not great.

We want to create another server that provides better forecasts, that take traffic into account. Too complicated? Maybe... So, that is not your task. You have a simpler task! All you need is to create a micro-service that can answer, given a pair of consecutive stops, what is the current average travel time between those stops.

Imagine, someone queries `YOUR-MS:8080/average_travel_time?from=f31423ab&to=f317ac2` and you need to answer `{'average_travel_time': 127.2}`. As simple as that. ;-)

Ok, you might be wondering: I don't know when a bus arrived at a stop, I only know when, sometime in the past, a system forecasted the bus would arrive. Well, life is hard, and we need to deal with the best information we have. So, to simplify things, you can assume the following: If a vehicle didn't produce new information about its arrival at a certain stop for 120 seconds or more, than the vehicle has already passed that stop, and you can safely assume it arrived at the latest forecasted time. I don't mean 120 seconds between you getting the information, but rather 120s between two forecast about the vehicle being produced.

You might also wonder: **average**? How big is a good moving average for this problem? Let's assume you can keep the last 8 measurements. However, measurements that are more than 10 minutes old should be discarded.

"Oh, what if I have no data for that stop pair? Or no data that is not too old?" Then do your best guess: return the current average of all stops you know.

There might be other corner issues, but we trust your judgement about how to deal with them.

### Details

You will need to:
* Create a local git repository
* Download the docker file provided from a link provided by e-mail: `serve.tar` 
* Create a microsservice to serve the needs above
* Submit your repo and any relevant comments

Please don't use any external storage services. In case you need a database, you are free to use an emulator from a testing framework of the language you chose. In case you need SQL, make your code deal with a SQLite file.

### Procedure to run the forecast server
1. Install and setup Docker
1. Install the docker image received separately: `docker load -i serve.tar`
1. Run the forecast server with `docker run -p 80:80 serve`
1. Query the forecasts by accessing `localhost:80/`

### Procedure to prepare your code
1. Start a git repository with ```git init```
1. Do your magic on your local machine, trying to commit often
1. Add your README, with instructions on how to run your code
1. Run ```git bundle create YOURNAME.bundle HEAD ```
1. Send the generated file by email back to your interviewer

## Evaluation criteria

Things we like:
* __Code readability, documentation and testing__ - We like code that is easy to read. PEP8 is a good start. Names for \
functions and variables should be self-explanatory. Documentation is good, but it is even better when it is not \
needed. Unit tests and doc-tests should be commonplace in production code, and can sometimes improve the reliability of \
analysis code. Same-order performance improvements are nice, but code simplicity is even nicer.
* __Understanding of the problem__ - Models should be build with a clear objective in mind. Evaluation metrics should be \
aligned with the objectives of the model. Understanding the real-life mechanics of the phenomena being modeled is crucial \
to coming up with the right approach.
* __Solution simplicity__ - Simpler code is easier to understand and more difficult to break. Less is more. Depending on \
fewer external components also makes everything easier and more reliable.
* __Performance__ - You should use the right data structures and access strategies. Your code should run fast enough for \
this specific application. However, you should not overengineer. Don't create a solution for 100x the current data volume if something simpler can still work well for 10x the current volume.

We want you to:
* Understand the problem
* Create a solution that fulfill the business needs
* Write a few tests and documentation, so we know you know how to do it
* Submit the repo with your working history

You don't need to:
* Try several different models to try to improve your score by subdecimal points
* Over-document or spend too much time writing tests
* Spend too much time overdoing it
* Spend too little time and write bad code

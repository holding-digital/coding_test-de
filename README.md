# Coding Challenge - Data Scientist

This repository was created to host the helper files for the Data Engineering role challenge.

The instructions below imply you have a minimum knowledge on how to run the Python data generator. That code will need to run to interact with your solution. This does not imply your solution too should be developed in Python. You are free to write your solution in the language of your preference within a short list we provide. However, we recommend you choose a language that you judge is the most appropriate for this kind of problem, taking into account easyness and time to develop, performance, and availability of libraries and connectors that might be helpful.

The languages you can consider as candidates for most appropriate ate:
* JavaScript
* Golang
* Python
* Scala

## The problem - Calculating real-time traffic in a bus network

X

### Details

For this task you can use any language of your choice for analysis and modeling. However you will need to integrate your \
model with the provided evaluation code in Python 3.

You will need to:
* Create a local git repository
* Download the Python files provided: `evaluate.py`, `file_evaluation.py` and `your_model.py` 
* Install Python 3 in a virtual environment
* Download the dataset for this task from your e-mail. (__Note:__ There is no limit on the time you need to return your \
solution. However that time will be taken into consideration when analyzing your solution.)
* Create a program to (re-)train and serialize a model to solve the problem.
* Create a program to use the trained model in the evaluation of additional data. (Integrate it in `your_model.py`)
* Submit your repo and your presentation within the deadline

### Procedure

1. Start a git repository with ```git init```
1. Install Python 3 and create a virtual env
1. Do your magic on your local machine, trying to commit often
1. Add your README, with instructions on how to run your code
1. Run ```git bundle create YOURNAME.bundle HEAD ```
1. Send the generated file by email back to your interviewer

### Evaluation tool usage

1. Install Python 3 and cd to the solution folder
1. Run ```virtualenv env```
1. Run ```. env/bin/activate``` (commands might differ depending on your OS)
1. Run ```pip3 install -r requirements.txt```
1. Create a subfolder and move the csv files for the days you want to evaluate
1. Run ```python3 evaluate.py SUBFOLDER_NAME```

## Presentation

We want you to create a small presentation (use Google Slides) summarizing your findings and answering a few questions. \
However the slides should be self-explanatory, be prepared to present your slides and answer additional questions.

Your findings should focus on any relevant facts about the problem or concerns about the quality of the service provided\
by the clinic.

The questions we want you to answer in your presentation are:
* Is it better to break down the problem into the forecasting of different components? Why?
* What is the relationship between patient temperature and consultation duration?
* Is there a relationship between time of the day and consultation duration? What could likely explain that?
* Apart from the assessment result (_normal_, _urgent_), what is the feature that is more relevant for the problem?
* What is your opinion about the scoring metric implemented in `evaluate.py`? Is there real-world support for it?
* If you had more days to work on the solution, how would you architect the solution?

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

# Edge Run Request Generator

This project provides ready-to-use request generators that the Galileo project uses to generate workload
(specifically, [faas-sim](https://github.com/edgerun/faas-sim) and [galileo-experiments](https://github.com/edgerun/galileo-experiments))

The project is structured simply and offers multiple generators that produce inter-arrival times.
Currently supported RPS profiles:

* Constant - does what you'd expect
* Sine - replicates a sine wave with a given peak (max rps) and period (simulation time in seconds between peaks)
* Randomwalk - creates a random walk pattern

RPS profiles yield a target average request per second pattern at a given time.


RPS profiles can be decorated using arrival profiles to get a more realistic request pattern.
Following arrival profiles are supported:

* Static
* Expovariate

You can save profiles using the helper function `save_requests` and `pre_recorded_profile` to read a saved profile
(only necessary if you like to plot it afterwards again).

# Install

To install dependencies and develop, run:

    make venv

This creates a virtual environment, activates it and installs all dependencies (`requirements.txt` and `requirements-dev.txt`).

If you like to run the notebooks (i.e., to generate request patterns and plot them comfortably):

    pip install -e .
    jupyter notebook

Note: you might have to restart the terminal session if `jupyter notebook` fails.
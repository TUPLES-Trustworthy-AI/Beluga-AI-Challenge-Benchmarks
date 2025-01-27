# Benchmark for Beluga Challenge

This repository provides an initial set of training instances for all challenges and tracks.
Participants are encouraged to generate additional instances if required.
Detailed instruction how to do so can be found in the [Toolkit Repository](https://github.com/TUPLES-Trustworthy-AI/Beluga-AI-Challenge-Toolkit). 

## Scalability Challenge

For the scalability challenge the folder structure looks as follows:

1. `deterministic`: training instances for deterministic track
2. `probabilistic`: training instances for probabilistic track
    - `arrivals`: with flights with stochastic delay
    - `ppddl`: with probabilities of transition between abstract states
3. `configuration_files`: configuration files for instance generator (see [Toolkit Repository](https://github.com/TUPLES-Trustworthy-AI/Beluga-AI-Challenge-Toolkit/blob/main-competition/README.md#problem-generator))

The training instances for the deterministic and the probabilistic track are equivalent except for the additional information about the uncertainty in the flight schedule. 

The provided instances have been generated with the initial seed `42`. 
More detailed information about the parameters space we consider for the competition can be found at the end of the toolkit repository [README](https://github.com/TUPLES-Trustworthy-AI/Beluga-AI-Challenge-Toolkit/blob/main-competition/README.md#benchmark-distributions).

## Explainability Challenge

For the explainability challenge the folder structure looks as follows:

1. `sample_instances`: a selection of pre-generated sample instances
    - `solvable`: Instances that are solvable (where it is possible to find a plan)
    - `unsolvable`: Instances that are unsolvable (where it is not possible to find a plan). 
        The file name indicates which infeasibility scenario was used to generate the instance.
        This naming convention is not guaranteed and must not be used to determine the cause of the unsolvability.
2. `sample_question`: a collection of sample questions for a given instance and plan.
    Files are named based on whether the used instance is solvable (`example_sat_questionXX.json`) or       
    unsolvable (`example_unsat_questionXX.json`).
    There can be multiple questions for the same solvable instance and plan.
3. `configuration_files`: configuration files for instance generator (see [Toolkit Repository](https://github.com/TUPLES-Trustworthy-AI/Beluga-AI-Challenge-Toolkit/blob/main-competition/README.md#problem-generator))

The provided instances, solvable and unsolvable, have been generated with the initial seed `42`.
The resulting instances were filtered based on whether [Fast Downward](https://www.fast-downward.org/)
with the `LAMA-first` configuration (a suboptimal but complete planner)
could find a plan or prove the task unsolvable within a timeout of 5min.
Instances for which no result was obtained within the timeout were skipped.

The sample questions are randomly generated based on what kind of question 
is applicable in a given instance and for a given plan.
Questions used in the final evaluation can be selected differently.

More detailed information about the parameters space we consider for the 
competition can be found at the end of the toolkit repository [README](https://github.com/TUPLES-Trustworthy-AI/Beluga-AI-Challenge-Toolkit/blob/main-competition/README.md#benchmark-distributions).

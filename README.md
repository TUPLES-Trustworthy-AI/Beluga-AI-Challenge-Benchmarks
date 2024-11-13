# Benchmark for Beluga Challenge

This repository provides an initial set of training instances for all challenges and tracks.
Participants are encouraged to generate additional instances if required.
Detailed instruction how to do so can be found in the [Tools Repository](TODO). 

## Scalability Challenge

For the scalability challenge the folder structure looks as follows:

1. `deterministic`: training instances for deterministic track
2. `probabilistic`: training instances for probabilistic track
    - `arrivals`: with flights with stochastic delay
    - `ppddl`: with probabilities of transition between abstract states
3. `configuration_files`: configuration files for instance generator (see [Tools Repository](TODO))

The training instances for the deterministic and the probabilistic track are equivalent except for the additional information about the uncertainty in the flight schedule. 

The provided instances have been generated with the initial seed `42`. 
More detailed information abound the parameters space we consider for the competition can be found at the end of the tools repository [README](TODO).

## Explainability Challenge

*Coming soon ...*

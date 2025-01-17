[![Linux/Mac/Windows build status](
  https://circleci.com/gh/dwave-examples/airline-hubs.svg?style=svg)](
  https://circleci.com/gh/dwave-examples/airline-hubs)

# Airline Hub Locations

A challenging optimization problem in the airline industry is determining which
airports should be hub locations for an airline. In this demo, we show how to
formulate this problem as a discrete quadratic model and use a hybrid solver to
optimize and find feasible solutions.

The goal for this problem is to minimize costs for the airline, while providing
transportation for all city pairs in demand by passengers.

## Running the Demo

To run the demo, type

`python demo.py`

The program will select 3 hubs out of a list of 25 different airports. The
information in the files `flow.csv` and `cost.csv` is used to determine the
optimal selection of hub airports, based on passenger flow and airline costs
found in these files.

A GIF will be produced that illustrates the feasible results found by the
hybrid solver, as shown below.

![output](readme_imgs/airline-hubs.gif)

## Formulating the Problem

In order to minimize costs, the airlines must consider several factors.

 1. The cost to operate a non-stop route (sometimes referred to as a leg). Note
that costs between hub airports are discounted.  
 2. The passenger demand for each leg (called the flow).

The demo reads in both of these factors from provided data files (`cost.csv`
and `flow.csv`, respectively).

We have several additional constraints that must be satisfied in order for a
route map to be feasible.

 1. Every leg must connect to a hub.  
 2. Passengers only connect at hub airports.  
 3. Only p hubs total.

The first two constraints ensure that any connecting airports are hubs.

## References

O'Kelly, Morton E. "A quadratic integer program for the location of interacting
hub facilities." European journal of operational research 32.3 (1987): 393-404.

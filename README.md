# Airport Security Queue Simulation Using SimPy
## Project Overview
This project simulates a simplified airport security screening system using discrete-event simulation. The objective is to determine the number of staff required at each security stage to keep average passenger wait times below 15 minutes while maintaining efficient resource utilization.

## System Description
The airport security process is modeled as a two-stage queueing system:

### 1. ID / Boarding Pass Check
- Multiple parallel servers
- Service time follows an exponential distribution
- Mean service time: 0.75 minutes

### 2. Personal Security Scanner
- Multiple parallel servers
- Passengers routed to the shortest available queue
- Service time follows a uniform distribution between 0.5 and 1.0 minutes

## Arrival Process
- Passengers arrive according to a Poisson process
- Arrival rate:
  - Standard scenario: λ = 5 passengers per minute
  - High-traffic scenario: λ = 50 passengers per minute

## Simulation Parameters
- Simulation runtime: 480 minutes (8 hours)
- Performance metric: Average total time in system
- Target constraint: Average wait time < 15 minutes
- Random seed set for reproducibility

## Experimental Setup
Multiple configurations were tested by varying:
- Number of ID checkers
- Number of personal security scanners

Tested configurations included:
- 3 ID checkers × 3 scanners
- 7 ID checkers × 7 scanners

## Results
- With 3 ID checkers and 3 scanners, the average wait time exceeded 15 minutes
- Increasing staffing to 7 ID checkers and 7 scanners reduced the average wait time below the target threshold

## Key Findings
- Parallel servers significantly reduce congestion
- Balanced staffing across stations prevents bottlenecks
- A configuration of 7 staff members per station provides sufficient buffer against arrival variability

## Recommendation
Deploy 7 ID checkers and 7 personal security scanners during normal operations, with additional standby staff available during peak traffic periods.

## Tools & Technologies
- Python
- SimPy
- Discrete-Event Simulation
- Queueing Systems

## How to Run
1. download and run airport_simulation.py

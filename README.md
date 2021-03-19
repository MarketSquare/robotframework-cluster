# robotframework-cluster
possible successor of Pabot

## Why
- Pabot is 5 years old now and it has code that does what it does. It is a one person hobby project.
- Pabot has room for improvement with exec time, because it starts a single robot per execution item.
- preserve global library instances for each Thread/Satellite. Not re-initializing the library instance for each test/suite.
- Pabot only runs on one local machine and we want to be able to distribute test to specific test envs. Conflicting requirements for different test envs.
- Load balancing pabot test over multiple machines.


## What
- There shall be a core team.
- There shall be centralized Hive with "distributor/coordinator/collector" and N "drones".
- Distributor creates a robot model, serializes it and sends it to the "drones".
- Coordinator takes care about what is executed and what shall be executed next
- Drones executes tests locally and communicates them with coordinator
- Result collector gets results from satellites and create one RobotResult
- Coordinator may start local satellites or register remote drones
- Drones shall be capable of being configured to execute tests that can be executed on that particular env.
- Tests shall be possible to not execute in order if test environments requires (i.e. one test env can only use specific tests)
- Drones shall be able to communicate and coordinate if common Setups have to be executed only once.
- Hive should be able to work with DataDriver or a similar functionality

- Container technologies shall be integrated, so that Hive may be able to control Kubernetes Cluster or Docker Containers.

## How

### Good Question


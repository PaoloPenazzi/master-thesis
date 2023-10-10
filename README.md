# Notes

## Ubiquitous Language
- Testing: the overall process carried out to verify and validate a system, according to requirements, in order to promote the desired internal and external quality, and to mitigate risks in development and products. [from cas benchmark paper]
- Testbed: a platform for rigorous transparent and replicable environment for experimentation and testing [AnastasiusGavras.2010.Experimentallydrivenresearchwhitepaper.tech.rep.,ICT-Fireworks(2010).]
- Solution: can consist of a set of algorithms leading to achieving goals and overcoming the problem posted (e.g. gradient)
- Scenario: contains all the information about the test execution: the simulation platform, the metrics, the input parameters..
- Metric: a measure (e.g. time to finish)

## On the language

Scala:
+ Great language features
- Slow compile time
- JVM dependent

Kotlin:
+ Multiplatform (JVM, Native, JS which could be useful)
+ Widespread
+ Scala's features but faster compile time

Rust:
+ Memory safety and efficiecy
+ A modern version of C with advanced feature
- Integration with other language is difficult

At this point, the best choice seems to be Kotlin which is the only language that i never used between the three :)

## Use case

- A user should be able to use a YAML/JSON file to define what he wants to do, without caring about
the system he's currently on, or the dependencies of the simulator he wants to use.
- The user should be able to see the result of the simulation.

## Requirements

These are not requirements requirements actually

- The Testbed should be inside a docker container. By doing so we abstract from the user's OS and 
assure that all requirements of the testbed are met.
- The container should be deployable on a server and accessible through a webpage.
- The user should be able to define everything he wants to do in a YAML/JSON file.
- Support for multiple scenario, execution and simulator platforms.

## Architecture

- DSL (?)
- A GUI to interact with the software (Not a priority, not necessary if we plan to deploy online)
- Parser to read the input YAML file [KAML](!https://github.com/charleskorn/kaml).
- Interfaces to enable the use of different simulators
- A component to launch simulations
- Listeners to read the results of the simulation and show them to the user.
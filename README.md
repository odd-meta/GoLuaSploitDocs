# GoLuaSploitDocs

## Architecture

Golang bot

pulls down lua bytecode from hardcoded target and runs bytecode in interpreter

### connection classes

realtime
 C&C server
 - issue command, get response data back immediately
DNS communication

non-realtime
 twitter
 - post a command, get response data back eventually


concept of high and low data rate communication classes, 


## Bot features

internal broadcast networking

possibly using multicast or some form of UDP broadcast

broadcast traffic use case:
phishing campaign compromises many hosts that are then able to discover each other internally without any host based communication

if bot fails to communicate initially with C&C have it start runnning discovery; manage to get an internal C&C, send out another wave of malware that points at the internal C&C,
discovery system from the previous wave is able to pick up the new bots from the second wave and changes to talk to the new internal C&C

have a spread of handler connection types across a single campaign that try different connection types

have internal bots discover each other

then elect a single bot to communicate with the external C&C


for other C&C mechanism, possibly hardcode IPs for non-real time data transports, github, twitter, etc

heuristic analysis of a host based on configuration settings, have different sets of behaviors associated with different levels of configuration
 - if DNS is set to external, detected AV is not enterprise, no exfil filtering
 - assume environment is weakly protected and less stealthy communication will likely not be detected


human layer denial of service features for IR departments in terms of creating a sacrificial bot to trigger as much IR as possible, calling out to fake https handlers, etc to take time away from IR against the actual attack; possibly trigger as a behavior on environments that are heuristicly detected as "locked down"


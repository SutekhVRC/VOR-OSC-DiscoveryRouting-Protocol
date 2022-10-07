# VOR-OSC-DiscoveryRouting-Protocol
Protocol thinking for VOR

## First thoughts

### Data type:
- Custom (binary) or JSON?
- Modded OSC

### Data Structures

- STATUS
```
- List apps {(apps id), (ports used by an app's route), (apps OSC L4 protocol [UDP/TCP])}
- Other data
```
- PUSH
```
- AppConfig (apps id), (ports used by an app's route), (apps OSC L4 protocol [UDP/TCP])
```
- PUSHACK
```
- SUCCESS/FAILURE
- SUCCESS (return accepted config)
- FAILURE (return declined config information)
```
### Flow
-> OSCAPP: STATUS

<- VOR: STATUS

-> OSCAPP: PUSH (app config)

<- VOR: SUCCESS/FAIL (Sets up route or not)

OSCAPP: Begins app routines or tries again

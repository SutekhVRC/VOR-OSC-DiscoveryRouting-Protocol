# VOR-OSC-DiscoveryRouting-Protocol
Protocol thinking for VOR

## First thoughts

- VOR will have a modular management port implementation to allow easy implementation of new management protocols
- A simple easy to use generic management protocol anyone can use from any language
- A more advanced compact / efficient protocol
- Other protocols

### Management Port
  - 86086
  - UDP

### Data type:
- UDP(JSON)
- Modded OSC

### Data Structures

- STATUS / STATUSACK
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

```
-> OSCAPP: STATUS

<- VOR: STATUS

-> OSCAPP: PUSH (app config)

<- VOR: SUCCESS/FAIL (Sets up route or not)

OSCAPP: Begins app routines or tries again
```

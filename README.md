# VOR-OSC-DiscoveryRouting-Protocol
Protocol thinking for VOR

## First thoughts
Data type:
- Custom (binary) or JSON?

## Flow
-> OSCAPP: STATUS
<- VOR: STATUS
-> OSCAPP: PUSH (app config)
<- VOR: SUCCESS/FAIL (Sets up route or not)
OSCAPP: Begins app routines or tries again

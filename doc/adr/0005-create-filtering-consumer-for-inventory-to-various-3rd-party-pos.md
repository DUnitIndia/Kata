# 5. Create Filtering consumer for all master and transaction data flows to various 3rd Party Pos

Date: 2020-11-02

## Status

Accepted

## Context

a few master data and key information has to be sent to different 3rd party pos systems. these pos sytems are only concerned about the information pertinent to them and not about info related to other kiosks/fridges which are in a different premises

## Decision

Publish the master data and key information  to a  domain specific topic and let the various consumers filter the messages for their nodes and consume

## Consequences

The advantage is that we wouldnt be required to have multiple topics/message queues for the various fridges. even assuming that we have say 500 fridges, this mechanim quickly leads to an explosion and the cost in terms of hardware involded and the monitoring, support soon outweighs benefits. Let the consumer filter the messages and discard what is not relevant. the tradeoff here is that the consumer has to consume lot of information (n/w calls , traffic cost etc.,)and then filter the relevant info. this seems an acceptable tradeoff at this point and can be visited later if the forces at play changes (cost, volume of updates, update currency of the info etc.,)